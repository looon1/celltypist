# Celltypist

**_Automated cell type annotation for scRNA-seq datasets_**

## Install

```console
pip install celltypist
```

## Usage

### Sample data and default model

```python
import celltypist

sample_input = celltypist.samples.csv()
result = celltypist.annotate(sample_input)
result.summary
```

### Using your own data

```python
import celltypist

input_data = "/path/to/cell_by_gene_matrix.csv"
result = celltypist.annotate(input_data)
result.summary.to_html("summary.html")
result.write_excel("annotation_result.xlsx")
```

### Using included models

```python
import celltypist

input_data = "/path/to/cell_by_gene_matrix.csv"
result = celltypist.annotate(input_data, model="immune")
result.write_excel("annotation_result.xlsx")
```

#### List models included in with the package

```python
import celltypist

available_models = celltypist.models.get_all()
available_models
```

### Use custom models

```python
import celltypist

indata = "/path/to/cell_by_gene_matrix.csv"
custom_model = "/path/to/custom_model.pkl"

result = celltypist.annotate(input_data, model=custom_model)
result.write_excel("annotation_result.xlsx")
```
