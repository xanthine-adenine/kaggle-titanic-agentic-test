Write a Python script to process the data in `data/train.csv` and `data/test.csv`. Assume that the only inputs will be `data/train.csv` or `data/test.csv`.

**The script must:**
- Take as an argument the name of a file in the `data/` directory and return an error if that file does not exist.
- Output the processed data as `<filename>_processed.pkl` (i.e. `pickle` the resulting dataframe) where `<filename>` is the name of the original file without any file extension.
- If `<filename>_processed.pkl` already exists, try to name it `<filename>_processed_<n>.pkl` where `<n>` starts at one and counts up until it does not correspond to an existing file.
- Process the data in the provided file in the manner described below and output the resulting data as a `.pkl` file.

**The processing steps are:**
- Retain the columns `PassengerId` and `Survived` unchanged.
- Binarize `Sex`: `"male"` = 0 and `"female"` = 1.
- Break `Pclass` into two binary columns:
    - `FirstClass`: `Pclass != 1` = 0 and `Pclass = 1` = 1
    - `SecondClass`: `Pclass != 2` = 0 and `Pclass = 2` = 1
- Create a `SpouseOnboard` column which is 1 iff exactly two rows exist whose `Name` column has the same last name and first name (disregard the title), but one has `Sex` = `"male"` and the other has `Sex` = `"female"`, otherwise the column's value is 0.
- Include no other columns than the ones mentioned in the final dataframe. Retain the names of the included columns unless otherwise specified.
