# CRCNet



## Run

0. Requirements:
    * Install python3.
    * Install [tensorflow](https://www.tensorflow.org/install/) (tested on Release 1.3.0, 1.4.0, 1.5.0, 1.6.0, 1.7.0).
    * Install tensorflow toolkit [neuralgym].
1. Training:
    * Prepare training images filelist and shuffle it ).
    * Modify [inpaint.yml](/inpaint.yml) to set DATA_FLIST, LOG_DIR, IMG_SHAPES and other parameters.
    * Run `python train.py`.
2. Resume training:
    * Modify MODEL_RESTORE flag in [inpaint.yml](/inpaint.yml). E.g., MODEL_RESTORE: 20180115220926508503_places2_model.
    * Run `python train.py`.
3. Testing:
    * Run `python test.py --image examples/input.png --mask examples/mask.png --output examples/output.png --checkpoint model_logs/your_model_dir`.
4. Still have questions?
    * If you still have questions (e.g.: How filelist looks like? How to use multi-gpus? How to do batch testing?), please first search over closed issues. If the problem is not solved, please open a new issue.





**Note:** Please make sure the mask file completely cover the masks in input file. You may check it with saving a new image to visualize `cv2.imwrite('new.png', img - mask)`.

## TensorBoard

Visualization on [TensorBoard](https://www.tensorflow.org/programmers_guide/summaries_and_tensorboard) for training and validation is supported. Run `tensorboard --logdir model_logs --port 6006` to view training progress.

## License

CC 4.0 Attribution-NonCommercial International

The software is for educaitonal and academic research purpose only.

## Citing

```
