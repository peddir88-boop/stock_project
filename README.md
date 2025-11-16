# Stock Project Automation Pipeline
# clean → aggregate → launch Streamlit
# -----------------------------------------

# Run full pipeline
run:
	python src/clean_data.py
	python src/agg.py
	streamlit run src/app.py

# Only clean data
clean:
	python src/clean_data.py

# Only generate aggregates
agg:
	python src/agg.py

# Launch Streamlit dashboard only
app:
	streamlit run src/app.py

# Install all dependencies
install:
	pip install -r requirements.txt

	import subprocess

def run(cmd):
    print(f"\n➡️ Running: {cmd}")
    subprocess.run(cmd, shell=True, check=True)

print("\n🚀 Starting Full Pipeline (Clean → Aggregate → Streamlit)...")

run("python src/clean_data.py")
run("python src/agg.py")
run("streamlit run src/app.py")

stock_project/
│
├── data/
├── src/
│   ├── clean_data.py
│   ├── agg.py
│   ├── app.py
│
├── Makefile          <-- ADD THIS
├── run_all.py        <-- ADD THIS
├── README.md
└── requirements.txt

