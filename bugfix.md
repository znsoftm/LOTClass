Thanks for letting me know the issue. I cannot reproduce the error on my machines but I believe it's related to the joblib parallel package. You could first try to reduce the number of workers by manually setting a smaller self.num_cpus:
LOTClass/src/trainer.py

Line 32 in aa65ae2
```
self.num_cpus = min(10, cpu_count() - 1) if cpu_count() > 1 else 1 

```
If it still doesn't work, you could modify the following code piece to remove the joblib part:
LOTClass/src/trainer.py

Lines 107 to 111 in aa65ae2
```
chunk_size = ceil(len(docs) / self.num_cpus) 
chunks = [docs[x:x+chunk_size] for x in range(0, len(docs), chunk_size)] 
results = Parallel(n_jobs=self.num_cpus)(delayed(self.encode)(docs=chunk) for chunk in chunks) 
input_ids = torch.cat([result[0] for result in results]) 
attention_masks = torch.cat([result[1] for result in results]) 
```
Specifically, you could simply replace the code above with
```
input_ids, attention_masks = self.encode(docs)
```
which does not use any parallelization, but it will circumvent the joblib issue.

Let me know if the problem still persists.

Thanks,
Yu