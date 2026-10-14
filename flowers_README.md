# Flowers Image Processing: Beginner to Intermediate

Two heavily commented Jupyter notebooks that teach classical image processing with OpenCV, using photos of flowers. Read the comments from top to bottom and run the cells to learn by doing.

## Dataset

[Kaggle: `alxmamaev/flowers-recognition`](https://www.kaggle.com/datasets/alxmamaev/flowers-recognition) — flower photos in five classes: `daisy`, `dandelion`, `rose`, `sunflower`, `tulip`. The notebooks download it with KaggleHub; the dataset is **not** stored in this repository.

```python
import kagglehub
dataset_path = kagglehub.dataset_download("alxmamaev/flowers-recognition")
```

## Notebooks

| Notebook | Level | Topics |
|---|---|---|
| `flowers_level1_image_processing.ipynb` | Beginner | Image as a grid of numbers, RGB channels, resize, crop, flip, rotate, brightness and contrast, grayscale and histogram, Gaussian blur, thresholding (fixed and Otsu), Canny edges |
| `flowers_level2_image_processing.ipynb` | Intermediate | Convolution and kernels, Sobel gradients, HSV and LAB colour spaces, colour masking, histogram equalization and CLAHE, noise and denoising (with PSNR), morphology, contours, a reusable "find the flower" pipeline, data types and memory |

Level 2 assumes you have completed Level 1. Each notebook ends with a recap table and *Try it yourself* exercises.

## Quick Start

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt

cd notebooks
jupyter notebook
```

Open a notebook and choose **Kernel → Restart & Run All**, or run the cells one at a time.

## Repository Structure

```text
.
├── notebooks/
│   ├── flowers_level1_image_processing.ipynb
│   └── flowers_level2_image_processing.ipynb
├── requirements.txt
├── README.md
└── .gitignore
```

Each notebook saves a summary figure to an `outputs/` folder next to it (`level1_overview.png`, `level2_overview.png`).

## Requirements and Notes

* Python 3.12 (the version the pinned packages were tested with) and the packages in `requirements.txt`.
* Kaggle access may require credentials; see the [KaggleHub documentation](https://github.com/Kaggle/kagglehub).
* The first run downloads the dataset; later runs reuse the cached copy.
* A CPU is enough. No GPU is needed.
* Choose a different flower by changing `CLASS_TO_STUDY` near the top of each notebook.
* The notebooks use a fixed random seed (`RANDOM_STATE = 42`), so the same image is selected every run.

## Limitations

* The pipelines in Level 2 are simple classical methods. They work best when the flower contrasts clearly with the background and can fail on cluttered scenes; the notebook encourages you to inspect the failures.
* The colour mask uses a fixed hue range for yellow and must be adjusted for other colours (red needs two ranges).

## Acknowledgements

Dataset: `alxmamaev/flowers-recognition` on Kaggle, accessed through KaggleHub. Please see its Kaggle page for the author and license terms.

## License

Add a license of your choice (for example MIT) before publishing.
