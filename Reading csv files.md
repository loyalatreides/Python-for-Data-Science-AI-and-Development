```python
import pandas as pd
```


```python
file = "FileExample.csv"
```


```python
df = pd.read_csv(file)
```


    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    Input In [3], in <module>
    ----> 1 df = pd.read_csv(file)
    

    File ~\anaconda3\lib\site-packages\pandas\util\_decorators.py:311, in deprecate_nonkeyword_arguments.<locals>.decorate.<locals>.wrapper(*args, **kwargs)
        305 if len(args) > num_allow_args:
        306     warnings.warn(
        307         msg.format(arguments=arguments),
        308         FutureWarning,
        309         stacklevel=stacklevel,
        310     )
    --> 311 return func(*args, **kwargs)
    

    File ~\anaconda3\lib\site-packages\pandas\io\parsers\readers.py:586, in read_csv(filepath_or_buffer, sep, delimiter, header, names, index_col, usecols, squeeze, prefix, mangle_dupe_cols, dtype, engine, converters, true_values, false_values, skipinitialspace, skiprows, skipfooter, nrows, na_values, keep_default_na, na_filter, verbose, skip_blank_lines, parse_dates, infer_datetime_format, keep_date_col, date_parser, dayfirst, cache_dates, iterator, chunksize, compression, thousands, decimal, lineterminator, quotechar, quoting, doublequote, escapechar, comment, encoding, encoding_errors, dialect, error_bad_lines, warn_bad_lines, on_bad_lines, delim_whitespace, low_memory, memory_map, float_precision, storage_options)
        571 kwds_defaults = _refine_defaults_read(
        572     dialect,
        573     delimiter,
       (...)
        582     defaults={"delimiter": ","},
        583 )
        584 kwds.update(kwds_defaults)
    --> 586 return _read(filepath_or_buffer, kwds)
    

    File ~\anaconda3\lib\site-packages\pandas\io\parsers\readers.py:482, in _read(filepath_or_buffer, kwds)
        479 _validate_names(kwds.get("names", None))
        481 # Create the parser.
    --> 482 parser = TextFileReader(filepath_or_buffer, **kwds)
        484 if chunksize or iterator:
        485     return parser
    

    File ~\anaconda3\lib\site-packages\pandas\io\parsers\readers.py:811, in TextFileReader.__init__(self, f, engine, **kwds)
        808 if "has_index_names" in kwds:
        809     self.options["has_index_names"] = kwds["has_index_names"]
    --> 811 self._engine = self._make_engine(self.engine)
    

    File ~\anaconda3\lib\site-packages\pandas\io\parsers\readers.py:1040, in TextFileReader._make_engine(self, engine)
       1036     raise ValueError(
       1037         f"Unknown engine: {engine} (valid options are {mapping.keys()})"
       1038     )
       1039 # error: Too many arguments for "ParserBase"
    -> 1040 return mapping[engine](self.f, **self.options)
    

    File ~\anaconda3\lib\site-packages\pandas\io\parsers\c_parser_wrapper.py:51, in CParserWrapper.__init__(self, src, **kwds)
         48 kwds["usecols"] = self.usecols
         50 # open handles
    ---> 51 self._open_handles(src, kwds)
         52 assert self.handles is not None
         54 # Have to pass int, would break tests using TextReader directly otherwise :(
    

    File ~\anaconda3\lib\site-packages\pandas\io\parsers\base_parser.py:222, in ParserBase._open_handles(self, src, kwds)
        218 def _open_handles(self, src: FilePathOrBuffer, kwds: dict[str, Any]) -> None:
        219     """
        220     Let the readers open IOHandles after they are done with their potential raises.
        221     """
    --> 222     self.handles = get_handle(
        223         src,
        224         "r",
        225         encoding=kwds.get("encoding", None),
        226         compression=kwds.get("compression", None),
        227         memory_map=kwds.get("memory_map", False),
        228         storage_options=kwds.get("storage_options", None),
        229         errors=kwds.get("encoding_errors", "strict"),
        230     )
    

    File ~\anaconda3\lib\site-packages\pandas\io\common.py:702, in get_handle(path_or_buf, mode, encoding, compression, memory_map, is_text, errors, storage_options)
        697 elif isinstance(handle, str):
        698     # Check whether the filename is to be opened in binary mode.
        699     # Binary mode does not support 'encoding' and 'newline'.
        700     if ioargs.encoding and "b" not in ioargs.mode:
        701         # Encoding
    --> 702         handle = open(
        703             handle,
        704             ioargs.mode,
        705             encoding=ioargs.encoding,
        706             errors=errors,
        707             newline="",
        708         )
        709     else:
        710         # Binary mode
        711         handle = open(handle, ioargs.mode)
    

    FileNotFoundError: [Errno 2] No such file or directory: 'FileExample.csv'



```python
df.columns = ['Name','Phone Number','Birthday']
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Input In [4], in <module>
    ----> 1 df.columns = ['Name','Phone Number','Birthday']
    

    NameError: name 'df' is not defined



```python

```
