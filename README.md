# FFenmass

FFenmass is a small simple python utility to encode directories and recreating them recursively, inspired by h265ize.







## Installation

Make the `install.sh` script executable and run

```bash
sudo ./install.sh
```
This will copy the `ffenmass` in your `/bin` directory

## Usage

`ffenmass` is transparent above `ffmpeg`, this means all `ffmpeg` syntax can be used with ffenmass as is , with the only exception being the input (`-i`) and the output being directories instead of files.

```bash
ffmpeg -i input.mkv -vcodec libx265 out.mkv


ffenmass -i /path/to/movies/ -vcodec libx265 /output/directory/
```

`ffenmass` will encode all media video files detected under the input directory and output them with the same folder structure and filenames in the output directory.

**Make sure your input/output directories have a trailing `/`**
```
/path/to/directory   #Is not a valid input

/path/to/directory/  #Is a valid input
```


## Contributing
Pull requests are welcome.Open an issue first to discuss what you would like to change.


## License
[MIT](https://choosealicense.com/licenses/mit/)
