# FFenmass

FFenmass is an FFmpeg python wrapper to manipulate media files in directories enmass and recreate them recursively, inspired by h265ize.
Currently works in **Linux** folder structures only.



### Dependencies
[`ffmpeg`](https://www.ffmpeg.org/)
[`rich`](https://github.com/willmcgugan/rich)


## Installation
```bash
pip3 install ffenmass
```
## Usage



`ffenmass` is transparent above `ffmpeg`, this means all `ffmpeg` syntax can be used with ffenmass as is ,
with the only exception being the input (`-i`) and the output being directories instead of files.
Because `ffenmass` ignores file extensions, you will need to specifify file container using ffmpeg's `-f` argument.




```bash
ffmpeg -i input.mkv -vcodec libx265 out.mkv


ffenmass -i /path/to/media/ -vcodec libx265 -f mkv /output/directory/
```



`ffenmass` will encode all video files detected under the input directory and output them with **the same folder structure and filenames** in the output directory.



**Make sure your input/output directories have a trailing `/`**
```
/path/to/directory   #Is not a valid input

/path/to/directory/  #Is a valid input
```


## Contributing
Open an issue first to discuss what you would like to change.

## TODO
 - Parse FFMPEG's output to create a progress bar
 - Find a way to make this work with 2 pass encoding
 - Clean up spaggeti
 - idk find more stuff to do

## Changelogs
 **0.2.1**
 
 - Recursive fix
 - FFmpeg made Verbose
 - Yaspin is no longer a dependency

 **0.2.0**
 
 - Ignores extensions, will now work with audio,video,subs etc.
 - Made into a pip module.

 **0.1.0**
 
 - Module was created and uploaded


## License
[MIT](https://choosealicense.com/licenses/mit/)
