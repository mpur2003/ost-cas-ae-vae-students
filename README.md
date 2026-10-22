# OST CAS: Autoencoders and Variational Autoencoders

Student materials for the 2026 class.

**[Download the complete student package](https://github.com/mpur2003/ost-cas-ae-vae-students/releases/download/course-2026/CASDay1_students_2026.zip)** — about 8.5 MB; no GitHub account needed.

1. Download **CASDay1_students_2026.zip** using the link above.
2. Extract the entire ZIP and keep its folders together.
3. Open **START_HERE.html** in your browser.

The slides and demonstrations work offline after extraction, with no Python installation, GPU, datasets or training required.

## Included

- 89 core lecture slides, ending with the take-home messages.
- Browser demonstrations for Digits, Fashion-MNIST and CelebA.
- Two Digits exercise notebooks and their solutions.
- Four standalone Fashion-MNIST/CelebA training notebooks with model summaries.
- Python/Jupyter setup, hardware choices and dataset download instructions.

The Fashion-MNIST/CelebA browser gallery uses labelled precomputed outputs. The small Digits decoder runs in JavaScript. The notebooks let you train your own models; optional Fashion-MNIST and CelebA training and downloads are disabled by default.

## Hands-on exercises

Read the [setup and dataset guide](STUDENT_GUIDE.md), then start Jupyter from the extracted package. The Digits exercises run on a laptop CPU. Try the exercises before opening their solutions.

Every model notebook includes a torchinfo summary. After creating the model in a Digits exercise, run **Inspect the model with torchinfo** to print its layers, tensor shapes and parameter counts without training.

The face models are optional. Their notebooks explain how to obtain CelebA from Kaggle and set the image and partition paths. Start with the small training limits when using limited hardware.

## Downloads and sources

Use the student ZIP in [Releases](https://github.com/mpur2003/ost-cas-ae-vae-students/releases), rather than GitHub's automatic source-code archive. The automatic archive contains this download page and notices.

SHA-256 checksums and a student release manifest accompany the ZIP. Teaching material and third-party assets retain their original credits; see [sources and notices](THIRD_PARTY.md).
