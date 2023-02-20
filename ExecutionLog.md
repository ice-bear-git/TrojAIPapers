# Execution Log


## TDteach
### 
* [Recipe of How to Run](https://github.com/csdongxian/ANP_backdoor/blob/main/recipe.md)
```Shell
tmux attach -t TDteach

# Done
CUDA_VISIBLE_DEVICES=5 python train_backdoor_cifar.py --poison-type badnets --poison-rate 0.05 --poison-target 0 --output-dir './save'

CUDA_VISIBLE_DEVICES=5 python train_backdoor_cifar.py --poison-type blend --poison-rate 0.05 --trigger-alpha 0.2 --poison-target 0 --output-dir './save'

# Next
python train_backdoor_cifar.py --poison-type clean-label --clb-dir './clb-data' --poison-target 0 --output-dir './save'

python optimize_mask_cifar.py --val-frac 0.01 --anp-eps 0.4 --anp-alpha 0.2 --checkpoints './save/last_model.th' --trigger-info' './save/trigger_info.th' --output-dir './save'

python prune_neuron_cifar.py --pruning-by threshold --pruning-step 0.05 --pruning-max 0.95 --mask-file './save/mask_values.txt' --checkpoints './save/last_model.th' --trigger-info' './save/trigger_info.th' --output-dir './save'

python prune_neuron_cifar.py --pruning-by number --pruning-step 20 --pruning-max 1000 --mask-file './save/mask_values.txt' --checkpoints './save/last_model.th' --trigger-info' './save/trigger_info.th' --output-dir './save'
```


## trojanZoo
* How to run

```Shell
tmux attach -t TrojanZoo

CUDA_VISIBLE_DEVICES=7 python ./examples/train.py --color --download --verbose 1 --dataset cifar10 --model resnet18_comp --lr_scheduler --cutout --grad_clip 5.0 --save
```


------------------


## Setup Git
```Shell
git remote set-url origin https://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@github.com/ice-bear-git/TrojAIPapers.git

# Repo URL: https://github.com/ice-bear-git/TrojAIPapers.git
# token: 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
```


## [SystemLevel]()
```Shell
nvidia-smi
```

## [SCLBD](https://github.com/SCLBD/Effective_backdoor_defense)
```Shell
conda activate Trojan
pip3 install -U opencv-python
pip3 install -U pyparsing
```


## [tmux](https://github.com/tmux/tmux/wiki#welcome-to-tmux)
* Prepare and Install
	- `brew install tmux` on the remote server!
	- `tmux new -sSCLBD` to open a new virtual session
	- `tmux new -sSCLBD_Eff` to open a new virtual session
    
* Detach and re-attach
    - To detach from a session, press `control^ + b` first, then press `d`
    - `tmux ls` to list all active tmux sessions
    - `tmux attach -t SCLBD` to resume;


## Execute iPynotebook in terminal

```Shell
# Create or re-attach to a virtual session
tmux new -s NR // tmux attach -t SCLBD

conda activate Trojan
export CUDA_VISIBLE_DEVICES=6; ipython -c "%run /scratch/ziang/round-10/projects/Trojan_Competition/src/Apply_noise/store_titration.ipynb"
```