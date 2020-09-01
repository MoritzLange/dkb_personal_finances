# Personal finance analysis for DKB accounts

This is a collection of notebooks for reading in and analysing credit card and
bank account data from DKB (Deutsche Kreditbank) accounts.

It is separated into three parts:

1. Read data from PDF and convert to pandas DataFrame
2. Annotate the data so that each expense has a category
3. Analyse the annotated data <br> (you might want to implement your own analysis code tailored to your requirements)

Each of these three steps has its own file. For steps 1 and 2, there
are one file for credit cards and one for account statements, since there
tables in the PDFs have different formats (affecting step 1), and then
the subjects also often look different (credit card subjects are more concise
and hence easier to assign to categories, affecting step 2).

**NB: If you fork this or in any other way upload your own version somewhere, make sure to remove all sensitive information from the source code! These include, amongst others, bank account numbers and (partial) credit card numbers!**

### Usage

In order to use this tool, do the following:

1. Install `pdfplumber` (it's the only requirement not included in anaconda)
2. Run `cc_pdfs_to_dataframe.ipynb` and `statement_pdfs_to_dataframe.ipynb`,
  after adjusting the file paths to the respective statements.
3. Go to the annotation files
  (`cc_data_annotation.ipynb` and `statement_data_annotation.ipynb`)
  and add meaningful substrings to each category. Repeat this step as
  instructed in the file, until no categories are unassigned (or if there
  are some still unassigned, they'll be ignored in step 3).

  If you add or remove categories, adjust relevant cells in `data_analysis.ipynb`
  as well, if you intend to use that file.
4. You now have the annotated data in a DataFrame. You can either write code to
  analyse it yourself, or you can use `data_analysis.ipynb` to see monthly rolling
  costs for each category and plot pie-charts of average costs for different time
  frames.


### Requirements
- `pdfplumber`
- `pandas`, `numpy` and some other common packages shipped with anaconda
