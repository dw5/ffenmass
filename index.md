## Encode directories with ffmpeg

### Prerequisites

 - `ffmpeg`
 - `ffpb` - Yeah I cant be bothered to make a ffmpeg loading bar, this works fine.
 - `tqdm`
 - `rich`


### Installation

Recommended way is using `pip`, as building from git can be unstable.
   ```bash
   pip3 install ffenmass
   ```


## Differences to FFmpeg Syntax

- **-i** - This needs to be a directory created beforehand, instead of a file.

- **output** - This needs to be a directory, instead of a file. If the directory does not exist it will be created. The output must be the last argument as per standard ffmpeg syntax.


- **-ext** - This is a custom argument, specific to **ffenmass**, here you will provide the extension you want for your files, examples `mp4,mkv,opus,mp3` , you only provide the extension and with no `.`, for further clarification, look at the command comparison below.

**!! Directories are required to have a trailing slash `/` !!**

The result is, **ffenmass** will **encode all media files detected under the input directory** with the provided ffmpeg arguments and output them with the **same folder structure and filenames** in the **output directory**.

<br>

### Example compared to standard ffmpeg syntax
```bash
ffmpeg -i input.mkv -vcodec libx265 -preset medium out.mp4


ffenmass -i /path/to/folder/ -vcodec libx265 -preset medium -ext mp4 /output/directory/
```
<br>
<br>

**Directory Tree visualization** of what is going on when you run the **command from the example above**.
```
/path/to/folder/                           /output/directory/
├── givemefolders/                        ├── givemefolders/      
│   ├── somefolder/                       │   ├── somefolder/
│   │   └── example_movie.mkv             │   │   └── example_movie.mp4
│   │   └── irrelevant_textfile.txt       │   │   
│   ├── another_example.mkv         →     │   ├── another_example.mp4
│   ├── morefolders/                      │   ├── morefolders/
│   │   └── a_lot_of_examples.ts          │   │   └── a_lot_of_examples.mp4  
│   └── documentary.mkv                   │   └── documentary.mp4
├── another_example.mkv                   ├── another_example.mp4
├── more-examples.mp4                     ├── more-examples.mp4 
└── examples_and_examples.ts              └── examples_and_examples.mp4

```



<br>


## License

Distributed under the MIT License. See `LICENSE` for more information.
