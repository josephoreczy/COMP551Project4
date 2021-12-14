#This repository subsumes the original papers repository and contains its original README detailing the project structure and the available commands.
#The structure of the codebase is sufficiently concise, note that the proxies: ma, ev, and tr for main eval and train respectively are additions made for purposes in this project.
#Below is a distillation of the commands used in this project and their descriptions:
    - 
**Note: the resultant pruned/trained model from a ma.py command will be stored in the relative path: pruned_nets/{description-of-model}.pth**
**Note: the resultant trained model from a tr.py command would be stored in the relative path: pretrained/{description-of-mode}.pth, but we do not employ the use of base-models**
*Below is the sequence of commands required to reproduce our Table 1:
    1. python ma.py --model vgg --pruning_type loss_based --prune_percent 65 --n_rounds 1
    2. python ma.py --model vgg --pruning_type loss_based --prune_percent 65 --n_rounds 25
    3. python ma.py --model resnet-34 --pruning_type loss_based --prune_percent 50 --n_rounds 1
    4. python ma.py --model resnet-34 --pruning_type loss_based --prune_percent 50 --n_rounds 25
    5. python ma.py --model vgg --pruning_type biased_loss --prune_percent 65 --n_rounds 1
    6. python ma.py --model vgg --pruning_type biased_loss --prune_percent 65 --n_rounds 25
    7. python ma.py --model resnet-34 --pruning_type biased_loss --prune_percent 50 --n_rounds 1
    8. python ma.py --model resnet-34 --pruning_type biased_loss --prune_percent 50 --n_rounds 25
    9. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_loss_based_65_temp_5.0_rounds_1_seed_0.pth
    10. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_loss_based_65_temp_5.0_rounds_25_seed_0.pth
    11. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_loss_based_50_temp_5.0_rounds_1_seed_0.pth
    12. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_loss_based_50_temp_5.0_rounds_25_seed_0.pth
    13. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_biased_loss_65_temp_5.0_rounds_1_seed_0.pth
    14. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_biased_loss_65_temp_5.0_rounds_25_seed_0.pth
    15. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_biased_loss_50_temp_5.0_rounds_1_seed_0.pth
    16. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_biased_loss_50_temp_5.0_rounds_25_seed_0.pth

*Below is the sequence of commands required to reproduce our Table 2:
    1. python ma.py --model vgg --pruning_type grasp --prune_percent 65 --n_rounds 1
    2. python ma.py --model vgg --pruning_type grasp --prune_percent 65 --n_rounds 25
    3. python ma.py --model resnet-34 --pruning_type grasp --prune_percent 50 --n_rounds 1
    4. python ma.py --model resnet-34 --pruning_type grasp --prune_percent 50 --n_rounds 25
    5. python ma.py --model vgg --pruning_type grad_preserve --prune_percent 65 --n_rounds 1
    6. python ma.py --model vgg --pruning_type grad_preserve --prune_percent 65 --n_rounds 25
    7. python ma.py --model resnet-34 --pruning_type grad_preserve --prune_percent 50 --n_rounds 1
    8. python ma.py --model resnet-34 --pruning_type grad_preserve --prune_percent 50 --n_rounds 25
    9. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_grasp_65_temp_5.0_rounds_1_seed_0.pth
    10. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_grasp_65_temp_5.0_rounds_25_seed_0.pth
    11. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_grasp_50_temp_5.0_rounds_1_seed_0.pth
    12. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_grasp_50_temp_5.0_rounds_25_seed_0.pth
    13. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_grad_preserve_65_temp_5.0_rounds_1_seed_0.pth
    14. python ev.py --model vgg --pruned True --test_acc True --model_path pruned_nets/vgg_grad_preserve_65_temp_5.0_rounds_25_seed_0.pth
    15. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_grad_preserve_50_temp_5.0_rounds_1_seed_0.pth
    16. python ev.py --model resnet --pruned True --test_acc True --model_path pruned_nets/resnet-34_grad_preserve_50_temp_5.0_rounds_25_seed_0.pth

Note: Our Repo does not contain .pth files, github seemingly has file-size limit, a number of repos were created somewhat chaotically, the above models are smattered throughout.
