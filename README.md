# Sample Python CI/CD Project

This is a simple Python project to demonstrate CI/CD integration with Jenkins and GitHub.

## Structure

- `app/main.py`: Core logic
- `tests/test_main.py`: Pytest unit tests
- `Jenkinsfile`: Jenkins pipeline definition

## Running Tests Locally

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
pytest
