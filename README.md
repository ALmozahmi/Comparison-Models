# Comparison-Models
Comparing old classical method of depth estimation to the deep-learning



Monocular Depth Estimation Benchmarking

This repository benchmarks various models for monocular depth estimation. Our primary focus is the hybrid SVM + XGBoost model, which demonstrates classical performance compared to deep learning methods. Other models included in the repository (e.g., Monodepth2, Randomforest) are provided as references and Its not our own model.


<h1>Features</h1>

Implements and benchmarks Random Forest, Monodepth2, MiDaS, and SVM + XGBoost for monocular depth estimation.
Evaluates models using Root Mean Squared Error (RMSE).
Uses a subset of NYU Depth V2 for training and evaluation.

    git clone <repository_url>
    cd <repository_directory>

    conda create -n depth_benchmarking python=3.10
    conda activate depth_benchmarking

    pip install -r requirements.txt


<h4>##Dataset</h4>

The dataset used is a subset of NYU Depth V2. You can download it from the following link:
https://www.kaggle.com/code/drmaxx/depth-prediction-with-sklearn/input
Depth Prediction Dataset (Kaggle)

###Dataset Structure

Note: The code files use paths specific to our local setup. Please update the paths to match your local directory structure for the models and datasets.
Ensure the dataset is organized as follows:

        data/
        ├── train/
        │   ├── images/
        │   ├── depths/

        
        ├── test/
            ├── images/
            ├── depths/




Models Implemented
1. Random Forest
    A regression-based model using RGB images as features and depth maps as labels.
2. Monocular Depth Estimation (Deep Learning)
    Benchmarks deep learning models like Monodepth2 or MiDaS.
3. SVM + XGBoost (Our Model)
    A hybrid approach using:
   SVM for initial feature transformation.
   XGBoost for robust depth prediction.



   Running the Code
Training

To train the SVM + XGBoost model, run:

python train_svm_xgboost.py --dataset_path data/ --output_path outputs/

Evaluation

To evaluate the trained models, run:

python evaluate_models.py --model_path outputs/svm_xgboost.pkl --test_data data/test/

    Note: Replace paths with your local directories.

    Results and Benchmarks

The models were evaluated using Root Mean Squared Error (RMSE). The benchmark results are:
Model	RMSE
Random Forest	104.33
SVM + XGBoost (Our Model)	25.02
Monocular Depth (DL)	5.70
Contributing

We welcome contributions! Follow these steps:

    Fork the repository.
    Make your changes.
    Submit a pull request for review.



MIT License

Copyright (c) 2024 ALmozahmi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
