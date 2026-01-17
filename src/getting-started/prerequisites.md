# Prerequisites

cloudexit runs locally and is executed directly from the repository.

Before running the first assessment, make sure your local Python environment is ready.

**Python version**

cloudexit requires Python 3.10+

Check your version:

```bash
python3 --version
```

**Virtual environment & pip**

We recommend using a virtual environment to avoid dependency conflicts:

```bash
python3 -m venv ./venv
source venv/bin/activate
```

Then install dependencies:

```bash
python3 -m pip install -r requirements.txt
```

Verify pip is available:

```bash
python3 -m pip --version
```

**Common issues**

***'python3: command not found'***

Install Python 3 using your OS package manager or from python.org.

***'pip install'***

Try upgrading pip:

```bash
python3 -m pip install --upgrade pip
```

***Virtual environment activation doesn’t work***

Make sure you run:

```bash
source venv/bin/activate
```

and confirm you see `(venv)` in your shell prompt.
