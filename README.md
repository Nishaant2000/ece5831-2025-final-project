project:
  title: Interpretable Hybrid Model for Visual Pattern Recognition
  course: ECE 5831 – Pattern Recognition and Neural Networks
  institution: University of Michigan–Dearborn
  academic_year: 2024-2025

  description: >
    This project investigates visual pattern recognition using both
    neural networks and classical pattern recognition techniques,
    with a strong emphasis on interpretability. A baseline CNN is
    combined with handcrafted features to form a hybrid model that
    improves transparency without sacrificing performance.

authors:
  - name: ""
    role: Student
    email: ""

resources:
  github_repository: ""           # TODO: GitHub repo URL
  demo_video_youtube: ""           # TODO: YouTube demo video link
  presentation_slides_drive: ""   # TODO: Google Drive slides link
  final_report_drive: ""          # TODO: Google Drive report PDF link
  dataset_drive: ""               # TODO: Google Drive dataset / README link

repository_structure:
  root:
    - README.md
    - data.yaml
    - final-project.ipynb
    - requirements.txt
    - src/

  src_files:
    - baseline_cnn.py
    - gradcam.py
    - explain_gradients.py
    - handcrafted_features.py
    - hybrid_model.py
    - train_utils.py
    - save_fashionmnist_tensor.py

dataset:
  name: Fashion-MNIST
  description: >
    Fashion-MNIST is a benchmark dataset consisting of grayscale images
    of clothing items, commonly used for evaluating pattern recognition
    and neural network models.

  image_properties:
    type: grayscale
    resolution: 28x28
    channels: 1

  classes:
    - T-shirt/top
    - Trouser
    - Pullover
    - Dress
    - Coat
    - Sandal
    - Shirt
    - Sneaker
    - Bag
    - Ankle boot

  size:
    training_samples: 60000
    test_samples: 10000
    total_samples: 70000

  acquisition:
    method: torchvision.datasets.FashionMNIST
    framework: PyTorch
    auto_download: true

  storage:
    local_directory: data/
    raw_format:
      - train-images-idx3-ubyte
      - train-labels-idx1-ubyte
      - t10k-images-idx3-ubyte
      - t10k-labels-idx1-ubyte
    processed_format:
      - fashionmnist_train_tensor.pt
    included_in_git: false

preprocessing:
  cnn_pipeline:
    resize: 224x224
    normalization:
      mean: 0.5
      std: 0.5

  handcrafted_features:
    hog:
      orientations: 9
      pixels_per_cell: [8, 8]
      cells_per_block: [2, 2]
    glcm:
      distances: [1, 2]
      angles: [0, 45, 90, 135]
      properties:
        - contrast
        - dissimilarity
        - homogeneity
        - energy
        - correlation

models:
  baseline_model:
    type: Convolutional Neural Network
    architecture: ResNet-18
    framework: PyTorch
    task: Image classification

  hybrid_model:
    type: Feature Fusion Model
    components:
      - CNN embeddings
      - HOG features
      - GLCM features
    classifier: Random Forest

interpretability:
  cnn_methods:
    - Grad-CAM
    - Saliency Maps
    - Integrated Gradients

  hybrid_methods:
    - Feature Importance
    - SHAP

evaluation:
  metrics:
    - Accuracy
    - Confusion Matrix

  comparison:
    baseline_vs_hybrid: true

execution:
  environment:
    python_version: ">=3.9"
    framework: PyTorch
    hardware_support:
      - CPU
      - Apple Metal (MPS)
      - CUDA (if available)

notes:
  - >
    Large datasets, trained models, and output visualizations are
    excluded from the GitHub repository due to size limitations.
  - >
    All experiments are reproducible using the provided scripts
    and final-project.ipynb notebook.
