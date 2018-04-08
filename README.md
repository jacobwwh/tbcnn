For java comment data

1. python code2ast/commands.py java --infile ../tbcnn-data/java/java100.json --out ../tbcnn-data/java/java100.pkl
2. python sampler/commands.py nodes --infile ../tbcnn-data/java/java100.pkl --outfile ../tbcnn-data/java/java100_nodes.pkl
3. copy node list from stdout to NODE_LIST in vectorizer/node_map
4. python sampler/commands.py trees --infile ../tbcnn-data/java/java100.pkl --outfile ../tbcnn-data/java/java100_trees.pkl
5. python vectorizer/commands.py ast2vec --in ../tbcnn-data/java/java100_nodes.pkl --out ../tbcnn-data/java/java100_embedding.pkl --checkpoint vectorizer/logs
6. python classifier/commands.py train --infile ../tbcnn-data/java/java100_trees.pkl --embedfile ../tbcnn-data/java/java100_embedding.pkl --learn_rate 0.1 --batch_size 2 --conv_feature 100 --epoch 1
7. python classifier/commands.py test --infile ../tbcnn-data/java/java100_trees.pkl --embedfile ../tbcnn-data/java/java100_embedding.pkl --learn_rate 0.1 --batch_size 2 --conv_feature 100 --epoch 1
