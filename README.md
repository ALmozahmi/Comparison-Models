<h1>Monocular Depth Estimation Benchmarking SVM + XGBoost Model</h1>
<p>Comparing Classical Methods of Depth Estimation to Deep Learning</p>

<p>This repository benchmarks various models for monocular depth estimation. Our primary focus is the <strong>SVM + XGBoost model</strong>, which demonstrates classical performance compared to deep learning methods. Other models included in the repository, such as <strong>Monodepth2</strong> (a deep learning model) and <strong>Random Forest</strong> (a classical machine learning model), are provided solely as references. These models are not developed by us and remain the intellectual property of their respective creators, with all rights reserved.</p>

<h1>Installation</h1>
<p>Implements and benchmarks Random Forest, Monodepth2, and SVM + XGBoost for monocular depth estimation.</p>

<pre>
git clone https://github.com/ALmozahmi/Comparison-Models.git
cd Comparison-Models
</pre>
<br>
<pre>
conda create -n depth_benchmarking python=3.10
conda activate depth_benchmarking
</pre>
<br>
<pre>
pip install -r requirements.txt
</pre>

<h2>Dataset</h2>
<h3>Depth Prediction Dataset (Kaggle)</h3>
<p>The dataset used is a subset of NYU Depth V2. You can download it from the following link:</p>
<p><a href="https://www.kaggle.com/code/drmaxx/depth-prediction-with-sklearn/input">https://www.kaggle.com/code/drmaxx/depth-prediction-with-sklearn/input</a></p>

<h3>Dataset Structure</h3>
<p>Note: The code files use paths specific to our local setup. Please update the paths to match your local directory structure for the models and datasets.<br>Ensure the dataset is organized as follows:</p>

<pre>
data/
├── train/
│   ├── images/
│   ├── depths/
├── test/
    ├── images/
    ├── depths/
</pre>

<h2>Models Implemented</h2>
<ul>
  <li><strong>Random Forest:</strong> A regression-based model using RGB images as features and depth maps as labels.</li>
  <li><strong>Monocular Depth Estimation (Deep Learning):</strong> Benchmarks deep learning models like <strong>Monodepth2</strong>.</li>
  <li><strong>SVM + XGBoost (Our Model):</strong>
    <ul>
      <li>SVM for initial feature transformation.</li>
      <li>XGBoost for robust depth prediction.</li>
        <h3>Key Features</h3>
<ul>
    <li>Evaluation using Root Mean Squared Error (RMSE).</li>
    <li>A subset of NYU Depth V2 dataset is used for training and evaluation.</li>
</ul>
    </ul>
  </li>
</ul>

<h2>Running the Code</h2>
<p><strong>Training + Evaluating (Pre-trained weights are loaded)</strong></p>
<p>To train and evaluate the SVM + XGBoost model, run:</p>

<pre>
python XGBOOST+SVM.ipynb --dataset_path data/ --output_path outputs/
</pre>
<p><strong>Note:</strong> Replace paths with your local directories.</p>

<h2>Results and Benchmarks</h2>
<p>The models were evaluated using <strong>Root Mean Squared Error (RMSE)</strong>.</p>

<table>
  <tr>
    <th>Model</th>
    <th>RMSE</th>
  </tr>
  <tr>
    <td>Random Forest</td>
    <td>104.33</td>
  </tr>
  <tr>
    <td>SVM + XGBoost (Our Model)</td>
    <td>25.02</td>
  </tr>
  <tr>
    <td>Monocular Depth (DL)</td>
    <td>5.70</td>
  </tr>
</table>

<h2>Contributing</h2>
<p>We welcome contributions! Follow these steps:</p>
<ol>
  <li>Fork the repository.</li>
  <li>Make your changes.</li>
  <li>Submit a pull request for review.</li>
</ol>

<h2>MIT License</h2>
<p>Copyright (c) 2024 ALmozahmi</p>

<p>Permission is hereby granted, free of charge, to any person obtaining a copy<br>
of this software and associated documentation files (the "Software"), to deal<br>
in the Software without restriction, including without limitation the rights<br>
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell<br>
copies of the Software, and to permit persons to whom the Software is<br>
furnished to do so, subject to the following conditions:</p>

<p>The above copyright notice and this permission notice shall be included in all<br>
copies or substantial portions of the Software.</p>

<p>THE SOFTWARE IS PROVIDE
