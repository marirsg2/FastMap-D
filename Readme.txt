
#----------How to run-------------
1) Paste your networkx diGraph pickled object in the folder
   "Graph Folder"
2) In the main script ("Fastmap_D", paste the name of the file
    along with the configuration parameters at the top.
3) Run it ! The results are currently printed out in a text file.
   you would have to write your own script to parse it. The NRMSD error is clearly indicated in the printout

!! Please make sure your Directed Graph is Strongly connected !!

our method does not handle Graphs where some pairs of nodes have paths in one direction (A->B)
and not in the other (B->A). We are working on relaxing this requirement, as
well adapting it for different applications like social network graph analysis,
path planning and the like.
If you're interesting in working with us, please email Satish Kumar Thittamaranahalli <tkskwork@gmail.com>


#----------Knobs to play with-------------
These might improve your performance.
1) Learning the intercept with Lasso
2) Sampling more data to learn the potential field function
3) Potential Field Function: Replace Lasso with Elastic Net, Ridge regression or OLS. For graphs with
    highly asymmetric/irregular shortest path distances, Lasso is the smart choice.
    If you can afford to train a neural network because of availability of time
    and computational resources, then do it.


#----------For Undirected Graphs-------------
The idea of using a potential field seems to work well for undirected graphs too.
We only did some preliminary results, but saw greater improvements with using
a potential field function for the last (Kth) dimension, as opposed to using yet
another dimension.