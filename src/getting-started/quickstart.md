# Quickstart

This guide helps you run your first cloudexit assessment in a few minutes.

**1) Clone the repository**

```bash
git clone https://github.com/escapecloud/cloudexit.git
cd cloudexit
```

**2) Create a virtual environment**

```bash
python3 -m venv ./venv
source venv/bin/activate
```

**3) Install dependencies**

```bash
python3 -m pip install -r requirements.txt
```

**4) Run the interactive CLI**

***Amazon Web Services (AWS)***

```bash
python3 main.py aws
```

***Microsoft Azure***

```bash
python3 main.py azure
```

cloudexit will guide you through selecting:
- a cloud provider (AWS or Azure)
- scope parameters (AWS Account, region, resource group)
- cloud exit strategy
- authentication method
- assessment type (basic, standard)
- assessment name (optional)

**5) Open the generated report**

Each assessment creates a new timestamped folder under `reports/`.

Open the generated `index.html` or `report.pdf` file in your browser.

---
**Next steps**

- Configure provider permissions and authentication:
  - [Required permissions](../cloud-providers/required-permissions.md)
  - [AWS](../cloud-providers/aws.md)
  - [Azure](../cloud-providers/azure.md)

- Use a configuration file for repeatable workflows:
  - [Config schema](../config/config-schema.md)
