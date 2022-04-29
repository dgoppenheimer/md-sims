# Using `nglview` in Colab

## NGLView in Colab Assignment

This assignment is focused on using `NGLView` in Colab notebooks to view protein structures.

### Learning Objectives

By the end of this assignment, students will be able to:

- Install `NGLView` in a Colab notebook.
- Load a protein structure file into `NGLView`.
- Display multiple representations of a protein and ligand.
- Save protein images as `.png` files.

## NGLView Notes

[nglview at GitHub](https://github.com/nglviewer/nglview)  
This may not work correctly on Google Colab to view trajectories.

[nglviewer](http://nglviewer.org/nglview/latest/)

I may need to install `nglview-js-widgets`, too, separately.

[nglview](http://nglviewer.org/nglview/latest/contributing.html)  

It should work in google colab now, see [this post](https://github.com/googlecolab/colab-cdn-widget-manager/pull/14)

## Installation

```py
!pip install -q nglview pytraj
from google.colab import output
output.enable_custom_widget_manager()
```

```py
import nglview
view = nglview.show_pdbid("3pqr")  # load "3pqr" from RCSB PDB and display viewer widget
view
```

## Usage

[nglview tutorial pdf](https://osscar-docs.readthedocs.io/_/downloads/en/latest/pdf/)  

From the [OxCompBio notebook](https://github.com/bigginlab/OxCompBio/blob/master/tutorials/MD/02_Protein_Visualization.ipynb). This did not work on Colab.

```py
# Import NGLView
import nglview

# Select as your protein the 1HSG pdb entry
protein_view = nglview.show_pdbid('1hsg')
protein_view.gui_style = 'ngl'

#Uncomment the command below to add a hyperball representation of the crystal water oxygens in grey
#protein_view.add_hyperball('HOH', color='grey', opacity=1.0)

#Uncomment the command below to color the protein according to its secondary structure with opacity 0.6
#protein_view.update_cartoon(color='sstruc', opacity=0.6)

# Let's change the display a little bit
protein_view.parameters = dict(camera_type='orthographic', clip_dist=0)

# Set the background colour to black
protein_view.background = 'black'

# Call protein_view to visualize the trajectory
protein_view
```

### Representations

```py
# reset representation
view.representations = []
view.parameters = {'theme': 'dark'}
view.add_representation('licorice', selection='not hydrogen')
view.add_representation('cartoon')
```

```py
view.add_representation('cartoon', selection='protein')

# or shorter
view.add_cartoon(selection="protein")
view.add_surface(selection="protein", opacity=0.3)

# specify color
view.add_cartoon(selection="protein", color='blue')

# specify residue
view.add_licorice('ALA, GLU')

# clear representations
view.clear_representations()

# update parameters for ALL cartoons of component 0 (default)
view.update_cartoon(opacity=0.4, component=0)

# remove ALL cartoons of component 0 (default)
view.remove_cartoon(opacity=0.4, component=0)

# Not using default representation
view = nv.show_file('your.pdb', default=False)
view.center()
view.add_rope()
```

### Properties

```py
# set the frame number
view.frame = 100

# parameters for the NGL stage object
view.stage.set_parameters(**{
    # "percentages, "dist" is distance too camera in Angstrom
    "clipNear": 0, "clipFar": 100, "clipDist": 10,
    # percentages, start of fog and where on full effect
    "fogNear": 0, "fogFar": 100,
    # background color
    "backgroundColor": "black",
})

# note: NGLView accepts both origin camel NGL keywords (e.g. "clipNear")
# and snake keywords (e.g "clip_near")

# parameters to control the `delay` between snapshots
# change `step` to play forward (positive value) or backward (negative value)
# note: experimental code
view.player.parameters = dict(delay=0.04, step=-1)

# update camera type
view.camera = 'orthographic'

# change background color
view.background = 'black'
```

### Viewing Trajectories

```py
# adding new trajectory
view.add_trajectory(traj)
# traj could be a `pytraj.Trajectory`, `mdtraj.Trajectory`, `MDAnalysis.Universe`,
# `parmed.Structure`, `htmd.Molecule` or derived class of `nglview.Trajectory`

# change representation
view[0].add_cartoon(...) # equal to view.add_cartoon(component=0)
view[1].add_licorice(...) # equal to view.add_licorice(component=1)
```

### Making Movies

```py
pip install moviepy

from nglview.contrib.movie import MovieMaker
movie = MovieMaker(view, output='my.gif', in_memory=True)
movie.make()
```

### Interactive Controls

- `scroll` (or `scroll wheel`) zoom scene
- `scroll-shift` move near clipping plane and far fog
- `drag-right click` pan/translate scene (this works with 3-button mouse, but not track pad on Mac)
- `drag-left click` rotate scene
- `clickPick-left click` auto view picked component element
- `left click` on the desired atom (or its representation) to center view on that atom

### Selection Language

See the [Selection Language](http://nglviewer.org/ngl/api/manual/selection-language.html) section of the [nglviewer documentation](https://nglviewer.org/ngl/api/manual/index.html).

[Visualizing macromolecules and grids in Jupyter Notebooks with nglview](https://www.blopig.com/blog/2020/06/visualising-macromolecules-and-grids-in-jupyter-notebooks-with-nglview/#more-5739)

Looks like `nglview` is good for MD trajectories and proteins.

## Other Resources

[Oxford Computational Biology Tutorials](https://github.com/bigginlab/OxCompBio/tree/master/tutorials/MD)

This site has some jupyter notebooks that include installing and using `nglview`. Also, the notebooks have some useful questions to ask students.

Here is an interactive `NGLViewer` you can embed in a website. It has the ability to convert PyMOL `.pse` files.

[MichelaNGLo](https://michelanglo.sgc.ox.ac.uk/michelanglo)

From [Advanced NGLView usage](https://projects.volkamerlab.org/teachopencadd/talktorials/T017_advanced_nglview_usage.html)

Some useful tips can be found in the posts on [Multiple poses in NGLView](https://blog.matteoferla.com/2021/02/multiple-poses-in-nglview.html?m=0).

### NMR files from RCSB

See [this issue](https://github.com/nglviewer/nglview/issues/765)

```py
v = nglview.show_pdbid('1d3z', default_representation=False)
v.center()
v.add_cartoon(color='residueindex')
v
```

#### show model 1

```py
view._remote_call('setSelection', target='compList', args=["/1"], 
               kwargs=dict(component_index=0))
```

#### show all models

```py
view._remote_call('setSelection', target='compList', args=["*"], 
               kwargs=dict(component_index=0))
```





### Contents in Practical

- First steps: make sure everything works!
    - Experiment with the interactive controls
- Basic API usage:
    - Show a structure using its PDB identifier
    - Show a structure using a local file
    - Saving the widget state as a screenshot for offline viewing
    - Customize the representations
    - Control representations by selections
    - Load more than one structure
    - Show and hide components


## R

