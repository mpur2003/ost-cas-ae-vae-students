# Your AE/VAE course materials

Extract the complete ZIP first. Keep its folders together. Open **START_HERE.html**.

## See the lecture and demonstrations

Open `lecture/slides/index.html`, `lecture/demo/chapter3.html` or
`lecture/demo/digits_8x8.html` in a current browser. These work offline after
extraction and need no Python, GPU, model training or datasets. If your browser
blocks local files, run `python start_class.py` from the extracted folder.
The student slides finish with the lecture's take-home messages.

The Fashion/CelebA gallery selects **precomputed** outputs. It does not measure
inference latency. The Digits demo runs its small decoder in JavaScript.
Instructor live generation, face PCA and attribute editing require the Python
backend, trained weights and, for face exploration, the locally downloaded data.
Those instructor services are separate from this browser-only student gallery.

## Run the exercises

Use Python 3.11 for the tested environment. Install the packages once while online.
On Windows, from the extracted folder, run:

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\python -m pip install torch==2.11.0 torchvision==0.26.0 --index-url https://download.pytorch.org/whl/cpu
.\.venv\Scripts\python -m pip install -r requirements-student.txt
.\.venv\Scripts\python -m jupyterlab
```

On macOS/Linux, use `python3.11 -m venv .venv` and `.venv/bin/python` instead.
On macOS install `torch==2.11.0 torchvision==0.26.0` from the default package
index. For an accelerator, choose a compatible build using the
[official PyTorch instructions](https://pytorch.org/get-started/previous-versions/).
Do not replace a working hosted-notebook PyTorch installation unnecessarily.

Open these notebooks in Jupyter and use Shift+Enter to run one cell:

1. `exercise/01_digits_AE_student.ipynb`
2. `exercise/02_digits_VAE_student.ipynb`
3. `exercise/03_convtranspose2d_walkthrough.ipynb`

The first two contain deliberate `TODO` questions. Run All stops at the first
unanswered question. This is expected. Solutions are in `solutions/`; their
training cells run short CPU jobs when executed. Try the exercises first.
The third notebook is a complete numerical walkthrough. Digits is bundled with
scikit-learn, so no dataset download or account is needed.

## Train the larger models later

`lecture/student_notebooks/` contains four self-contained programs:

| Notebook | Model | Default behaviour |
| --- | --- | --- |
| 01 | Fashion-MNIST AE, 32×32 | Architecture and torchinfo summary |
| 02 | Fashion-MNIST VAE, 32×32 | Architecture and torchinfo summary |
| 03 | Foster CelebA VAE, 32×32 | Architecture and torchinfo summary |
| 04 | Raschka CelebA VAE, 128×128 | Architecture and torchinfo summary |

They default to `RUN_TRAINING=False`. Missing datasets and trained student
checkpoints are explained and skipped. Existing checkpoints in your student
workspace can be loaded. The package does not include pretrained notebook weights.

For Fashion-MNIST, set `DOWNLOAD=True` once while online to obtain the data.
Set `RUN_TRAINING=True` to train. For CelebA, follow the notebook's Kaggle
instructions and set the two data paths before enabling training. A GPU is
useful for the face models, particularly 128×128. All notebooks support CPU;
start with the small limits and lower the batch size if memory is limited.

Results are written to `chapter3_student_work`, separate from the demonstrations.
To resume, keep `RUN_NAME`, set `RESUME_TRAINING=True` and choose the number of
additional `EPOCHS`. Back up this workspace when using a temporary cloud runtime.
The notebooks contain their complete model and training code and can also be
copied individually to a hosted notebook service.

## What data must I obtain?

| Use | Separate download |
| --- | --- |
| Slides and both browser demos | None |
| Digits exercises and solutions | None after installing scikit-learn |
| Fashion-MNIST training | Notebook downloads it when `DOWNLOAD=True` |
| CelebA training | Download aligned images and the official partition metadata yourself |

The [Kaggle CelebA page](https://www.kaggle.com/datasets/jessicali9530/celeba-dataset)
provides the archive used in class. Extract it fully. Locate the inner folder
containing `000001.jpg`, `000002.jpg`, etc., often
`img_align_celeba/img_align_celeba/`, and `list_eval_partition.csv`.
Point `IMAGES_DIR` directly at the JPG folder and `PARTITION_FILE` at that CSV.
The notebooks read the original CSV directly. They also accept the official TXT.
Both face notebooks can share one dataset download. Attributes are unnecessary
for basic VAE training. Review the
[original dataset agreement](https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html).
Original CelebA photographs are not bundled in the student gallery or dataset.

## Common problems

- **A notebook is plain JSON in the browser:** open it through Jupyter.
- **No GPU:** choose `DEVICE_NAME='cpu'`. The Digits exercises use CPU already.
- **Wrong GPU/Python environment:** select the Jupyter kernel where you installed PyTorch.
- **No trained student checkpoint:** leave training off to inspect the architecture, or enable training explicitly.
- **Missing Python module:** run the requirements install in the same environment as the notebook kernel.
- **Missing `data.py` / `models.py`:** keep the whole extracted package for the Digits exercises.
- **Running cells out of order:** restart the kernel, then run from the top.
- **Face data not found:** check the nested image folder and the `.csv`/`.txt` path.
