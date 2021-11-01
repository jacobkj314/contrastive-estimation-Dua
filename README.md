# Contrastive Estimation

The main file is ropes_ablations.py where the class name for the model can be provided in model_class variable

To run a specific CE model, change the datafile paths and pretrained asnwering model path in configs/ropes_config.py.
Then start training the CE model with

python3 -m torch.distributed.launch --nproc_per_node=4 ropes_ablations.py --model_checkpoint <pretrained answering path> --output_dir <output_path>

If it is a new dataset and you don't have an answering model for it, then it can be trained by

python3.6 -m torch.distributed.launch --nproc_per_node=4 run_quoref_answering_model.py --model_checkpoint t5-large --output_dir /extra/ucinlp0/ddua/quoref/quoref_answer_model_large --n_epoch 15 --lr 5e-5 --max_context_length 650
