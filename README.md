# Source_in_graph

Algorithm for finding source in graph/network. Every node has a list of hashtags and times when certain hashtag occure in certain node/user. It randomly choose the specific number of observers and for all choosen observers there is a backward checking of timestamp for specified hashtag. If there is no neighboor with earlier timestamp the node is choose as a source.

```
#hashtag, number of observers, graph
def sources(tag,n,g):
    print("Hasztag: ",tg)
    node_list = list()
    hops_list = list()
    times_list = list()
    a_l = list()
    single_n = list()
    a = rep_node_set(n,g,tag)
    for (i, time) in a:
        b =  find_source(g,i,tag)
        node_list.append(b[0])
        hops_list.append(b[1])
        times_list.append(b[2])
        single_n.append(b[3])
        a_l.append(i)
    dicto = dict(Counter(node_list))
    node_list_final=[i for i in dicto.keys()]
    print("Wylosowani obserwatorzy: ",a_l)
    print("Znalezione źródła: ",node_list_final)
    return len(node_list_final), single_n.count(1), times_list, hops_list
```

Also there is a combined function to generate statistics about hops, isolated nodes, times and number of finded sources
```
#tag, number of random choose observers, number of iterations, graph
def research(tg,n,i,g)
```
**Needed files with infos from Twitter Network are there:**</br> https://drive.google.com/open?id=1FD9qBn3xmqd4tOQ9aktMSR8n1bciEBK5
bigdata2.csv - it contains all tag, node, time</li><br/>
- node_tt - dictionary in pickle for loading attributes to networkx graph<br/>
- node_tt - dictionary in pickle for loading attributes to networkx graph<br/>
- follower_gcc.anony.dat - file with graph structure<br/>

You can also use algorithm for your own generated graph with multiple attributes that are stored as a list of tuples (time,attribute).<br/>
Examples:<br/>
- The only source is node 0 and number of observers is 2<br/>
![example1](https://user-images.githubusercontent.com/18172067/43896562-86bd804a-9bd9-11e8-8770-dc71046a0647.JPG)<br/>
- The sources are 0, 1, 3 and number of observers is 2<br/>
![example2](https://user-images.githubusercontent.com/18172067/43896563-86dbe09e-9bd9-11e8-8b70-7887e51e9c07.JPG)<br/>
- The sources are 0, 1, 3 and number of observers is 3<br/>
![example3](https://user-images.githubusercontent.com/18172067/43896564-86fb6112-9bd9-11e8-97e3-c9fbb9929919.JPG)




