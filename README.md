# Cats-and-dogs-ML-
Cats and Dogs Image Classification

This project focuses on image classification of cats and dogs using a dataset provided by FreeCodeCamp. The dataset is split into training, validation, and test sets, each containing images of cats and dogs. The goal is to train a model to distinguish between images of cats and dogs.

 Dataset

The dataset can be downloaded and unzipped using the following commands:

```bash
!wget https://cdn.freecodecamp.org/project-data/cats-and-dogs/cats_and_dogs.zip
!unzip cats_and_dogs.zip
```

## Directory Structure

The unzipped dataset contains the following directories:
- `train`: Training set with subdirectories `cats` and `dogs`.
- `validation`: Validation set with subdirectories `cats` and `dogs`.
- `test`: Test set with images.

 Code Explanation

The provided code performs the following tasks:

Set Paths: Define the paths for training, validation, and test directories.

    ```python
    PATH = 'cats_and_dogs'

    train_dir = os.path.join(PATH, 'train')
    validation_dir = os.path.join(PATH, 'validation')
    test_dir = os.path.join(PATH, 'test')
    ```

   Count Images: Calculate the total number of images in the training, validation, and test directories.

    ```python
    total_train = sum([len(files) for r, d, files in os.walk(train_dir)])
    total_val = sum([len(files) for r, d, files in os.walk(validation_dir)])
    total_test = len(os.listdir(test_dir))
    ```

   Count Images in Specific Class: Define a function to count the number of images in a specific class within the test set.

    ```python
    def count_images_in_class(test_dir, class_name):
        class_dir = os.path.join(test_dir, class_name)
        if os.path.exists(class_dir):
            return len(os.listdir(class_dir))
        else:
            return 0
    ```

4. Set Hyperparameters: Define hyperparameters for pre-processing and training the model.

    ```python
    batch_size = 128
    epochs = 15
    IMG_HEIGHT = 150
    IMG_WIDTH = 150
    ```

Count Images in 'cats' Class: Use the function to count the number of images in the 'cats' class within the test set and print the result.

    ```python
    class_name = 'cats'  # Replace with the class name you're interested in
    num_images = count_images_in_class(test_dir, class_name)
    print(f"{num_images} images found in class 1 in test set.")
    ```

 Usage

To run the code, make sure you have the dataset downloaded and unzipped in the current working directory. Execute the Python script to count the number of images and perform any further processing or model training as needed.

 Future Work

- Implement data augmentation techniques to improve model performance.
- Train a Convolutional Neural Network (CNN) on the dataset.
- Evaluate the model on the validation and test sets.
- Optimize hyperparameters for better accuracy.

