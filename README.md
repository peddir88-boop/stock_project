# -----------------------------------------
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
