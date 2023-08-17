1. get_selected_bbv.py
    - Select the corresponding bbv from the overall bbv file according to the specified interval position to form a new file
    - Usage: ./get_selected_bbv.py total_bbv.bb selected_interval respath
        - total_bbv.bb: the raw bbv file that contains the bbv value of each interval
        - selected_interval: the file that contains the postions of all selected intervals
        - respath: the directory of the new generated bbv file

2. back_interval_index.py
    - Since the position of the representative intervals obtained by using the new bbv file for cluster analysis is the position in the new bbv file, it is necessary to reorient the position to the position in the original bbv file according to the selected_interval file
    - Usage: ./back_interval_index.py simpointfile weightfile selected_interval respath
        - simpointfile, weightfile: the result files generated by the clustering analysis. simpointfile contains the postion of selected intervals, and weightfile contains the weight of each selected interval.
        - selected_interval: the file that used by the get_selected_bbv.py script

3. combine_cluster_res.py
    - combine the result files generated by the clustering analysis to a single file
    - Usage: ./combine_cluster_res.py simpointfile weightfile