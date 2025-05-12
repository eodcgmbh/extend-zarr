# Extend Zarr

Library for writing a new DataArray to a Zarr file containing a DataArray
If necessary, the Coordinates of the DataArray in the Zarr file is extended and
the DataArray data is written.

## Usage

```python
from extend_zarr import extend_zarr

dataarray = ...  # DataArray to be written
zarr_path = ...  # Path to the Zarr file
extend_zarr(dataarray=dataarray,
            zarr_path=zarr_path,
            var_name='value')
```

## Limitations

The following limitations exists to the coordinates of the dataarray to which
this function can be applied.

- Coordinates needs to be unique 1D arrays.
- Dataarray can only be appended to tail of the zarr store.


## Development

Pixi is used for development and testing. To install the development environment,
run the following command:

```bash
curl -fsSL https://pixi.sh/install.sh | sh
```


Format the code with:

```bash
pixi run --environment development style
```

To test the package, run:

```bash
pixi run test
```

Test with different zarr versions with:

```bash
# test with zarr2
pixi run --environment test-zarr2 test
# test with zarr3
pixi run --environment test-zarr3 test
```

To start Jupyter Lab, run:

```bash
pixi run --environment development jupyter lab
```

Run the following command to start environment in development mode:

```bash
pixi shell --environment development
```
