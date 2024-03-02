# sliding-window-analysis

![Example plot](sliding_window_plot.png)

### Setup and run instuctions

1) Download or clone this repository.
   
2) Move or copy the directory containing the FASTA files you wish to analyze into the `sliding-window-analysis` directory, in a sub-directory named 'aligns'.

4) Open a command line interface and change your working directory to the sliding-window-analysis directory, for example

        cd example/path/to/directory/sliding-window-analysis

<!-- Build the docker image and specify the path to the directory containing your [FASTA files](https://en.wikipedia.org/wiki/FASTA_format) (note: the FASTA file directory must be in the sliding-window-analysis directory)

    docker-compose build --build-arg path_to_data=sliding-window-analysis/example/path/ -->


This version of the code works with the following python and python package versions:
python 3.11.8
pandas 2.0.3
numpy 1.24.3
scipy 1.11.1
bokeh 3.2.1

Other versions might work, but haven't been fully tested. 

Run the program, from within your sliding-window-analysis directory, as follows:

    python3 run.py path_to_data target window_size n_largest --stride --colors

For example, to look for asparagine enrichments in a 20-residue sliding window with a 5-residue stride:

    python3 run.py aligns/ N 20 50 --stride 5

Or, to look for aspartate and glutamate enrichments in 9-residue sliding widow with a default stride (1):

    python3 run.py aligns/ DE 9 50
