agnews:

Label names used for each class are: {0: ['politics'], 1: ['sports'], 2: ['business'], 3: ['technology']}
Some weights of the model checkpoint at bert-base-uncased were not used when initializing LOTClassModel: ['bert.pooler.dense.weight', 'bert.pooler.dense.bias', 'cls.seq_relationship.weight', 'cls.seq_relationship.bias']
- This IS expected if you are initializing LOTClassModel from the checkpoint of a model trained on another task or with another architecture (e.g. initializing a BertForSequenceClassification model from a BertForPretraining model).
- This IS NOT expected if you are initializing LOTClassModel from the checkpoint of a model that you expect to be exactly identical (initializing a BertForSequenceClassification model from a BertForSequenceClassification model).
Some weights of LOTClassModel were not initialized from the model checkpoint at bert-base-uncased and are newly initialized: ['cls.predictions.decoder.bias', 'dense.weight', 'dense.bias', 'classifier.weight', 'classifier.bias']
You should probably TRAIN this model on a down-stream task to be able to use it for predictions and inference.
Loading encoded texts from datasets/agnews/train.pt
Loading texts with label names from datasets/agnews/label_name_data.pt
Loading encoded texts from datasets/agnews/test.pt
Contructing category vocabulary.
100%|███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 62/62 [11:21<00:00, 10.99s/it]
Class 0 category vocabulary: ['politics', 'political', 'politicians', 'government', 'elections', 'politician', 'democracy', 'democratic', 'governing', 'party', 'state', 'leadership', 'election', 'politically', 'affairs', 'issues', 'governments', 'voters', 'debate', 'cabinet', 'congress', 'democrat', 'administration', 'president', 'religion', 'republican', 'history', 'crisis', 'war', 'legislature', 'candidates', 'governance', 'pr', 'opposition', 'problems', 'relations', 'finance', 'justice', 'struggle', 'rhetoric', 'right', 'convention', 'votes', 'fighting', 'violence', 'senate', 'matters', 'fight', 'us', 'parliament', 'republicans', 'trouble', 'one', 'conflict', 'soil', 'voting', 'law', 'parliamentary', 'representation', 'house', 'reality', 'wars', 'campaign', 'contest', 'candidate', 'campaigns', 'legislative', 'transition', 'question', 'choice']

Class 1 category vocabulary: ['sports', 'games', 'sporting', 'athletics', 'game', 'national', 'news', 'athletic', 'espn', 'soccer', 'stadium', 'basketball', 'arts', 'racing', 'baseball', 'tv', 'hockey', 'pro', 'press', 'team', 'red', 'home', 'bay', 'kings', 'legends', 'city', 'winning', 'miracle', 'olympic', 'go', 'giants', 'champions', 'ball', 'players', 'boxing', 'prime', 'teams', 'athletes', 'tennis', 'club', 'blue', 'coaches', 'gold', 'west', 'toronto', 'classic', 'pittsburgh', 'super', 'nfl', 'magic', 'key', 'times', 'field', 'warriors', 'rogers', 'stars', 'gym', 'championship', 'losses', 'college', 'mlb', 'veterans', 'rugby', 'hits', 'sun', 'bc', 'events', 'south', 'nba']

Class 2 category vocabulary: ['business', 'businesses', 'trade', 'commercial', 'enterprise', 'shop', 'money', 'market', 'commerce', 'corporate', 'global', 'future', 'sales', 'general', 'group', 'retail', 'companies', 'management', 'operations', 'operation', 'corporation', 'store', 'division', 'firm', 'venture', 'brand', 'contract', 'revenue', 'economic', 'branch', 'subsidiary', 'personal', 'cash', 'short', 'line', 'bank', 'customer', 'concern', 'growth', 'chain', 'strategic', 'family', 'work', 'products', 'big', 'scientific', 'virtual', 'engineering', 'sector', 'trading', 'portfolio', 'ceo', 'segment', 'investment', 'working', 'executive', 'private', 'services', 'public', 'job', 'marketing']

Class 3 category vocabulary: ['technology', 'technologies', 'tech', 'software', 'technological', 'device', 'equipment', 'hardware', 'infrastructure', 'devices', 'system', 'knowledge', 'technique', 'digital', 'technical', 'concept', 'systems', 'gear', 'techniques', 'material', 'functionality', 'process', 'facility', 'feature', 'capability', 'content', 'method', 'security', 'ability', 'network', 'internet', 'computing', 'chip', 'smart', 'modern', 'communication', 'language', 'mechanism', 'computer', 'design', 'cyber', 'standard', 'tool', 'development', 'format', 'protocol', 'wireless', 'phone', 'information', 'program', 'ce', 'plant', 'large', 'data', 'project', 'application', 'theory', 'science', 'performance', 'common', 'os', 'ict', 'speed', 'sensor', 'capabilities', 'electronic', 'society', 'silicon', 'invention', 'memory']

Preparing self supervision for masked category prediction.
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 938/938 [16:04<00:00,  1.03s/it]
Number of documents with category indicative terms found for each category is: {0: 211, 1: 1365, 2: 1426, 3: 2049}
There are totally 5051 documents with category indicative terms.

Training model via masked category prediction.
Epoch 1:
100%|███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 79/79 [03:38<00:00,  2.77s/it]
Average training loss: 0.8421313166618347
Epoch 2:
100%|███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 79/79 [01:31<00:00,  1.15s/it]
Average training loss: 0.26666104793548584
Epoch 3:
100%|███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 79/79 [01:30<00:00,  1.15s/it]
Average training loss: 0.14360524713993073

Start self-training.
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:55<00:00,  1.15s/it]
lr: 5.336e-07
Average training loss: 0.12905345857143402
Test acc: 0.8309210538864136
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 9.925e-07
Average training loss: 0.09212205559015274
Test acc: 0.8428947329521179
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 9.332e-07
Average training loss: 0.0873199924826622
Test acc: 0.8486841917037964
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 8.739e-07
Average training loss: 0.07891865819692612
Test acc: 0.8535526394844055
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 8.147e-07
Average training loss: 0.0704721063375473
Test acc: 0.855394721031189
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:55<00:00,  1.15s/it]
lr: 7.554e-07
Average training loss: 0.06378819793462753
Test acc: 0.8557894825935364
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:55<00:00,  1.15s/it]
lr: 6.961e-07
Average training loss: 0.06119184195995331
Test acc: 0.856184184551239
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 6.368e-07
Average training loss: 0.060733821243047714
Test acc: 0.8551315665245056
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 5.775e-07
Average training loss: 0.05740782618522644
Test acc: 0.856184184551239
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:55<00:00,  1.15s/it]
lr: 5.182e-07
Average training loss: 0.0543331541121006
Test acc: 0.8567105531692505
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 4.589e-07
Average training loss: 0.05330723151564598
Test acc: 0.8551315665245056
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 3.996e-07
Average training loss: 0.05650094524025917
Test acc: 0.8542105555534363
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:55<00:00,  1.15s/it]
lr: 3.403e-07
Average training loss: 0.05124599486589432
Test acc: 0.8527631759643555
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 2.81e-07
Average training loss: 0.05123397707939148
Test acc: 0.8526315689086914
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 2.217e-07
Average training loss: 0.05117468535900116
Test acc: 0.8531578779220581
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:55<00:00,  1.15s/it]
lr: 1.625e-07
Average training loss: 0.05488729849457741
Test acc: 0.8522368669509888
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:55<00:00,  1.15s/it]
lr: 1.032e-07
Average training loss: 0.055627837777137756
Test acc: 0.8513157963752747
100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 100/100 [01:54<00:00,  1.15s/it]
lr: 4.388e-08
Average training loss: 0.047273073345422745
Test acc: 0.850789487361908
Saving final model to datasets/agnews/final_model.pt





