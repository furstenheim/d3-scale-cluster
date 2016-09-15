# d3-scale-cluster
D3 scale that clusters data into discrete groups

###Usage

This scale largely has the same API as [d3.scaleQuantile](https://github.com/d3/d3-scale/blob/master/README.md#scaleQuantile) (however we use `breaks()` instead of `quantiles()`)

```js
var scale = d3.scaleCluster()
    .domain([1, 2, 4, 5, 12, 43, 52, 123, 234, 1244])
    .range(['#E5D6EA', '#C798D3', '#9E58AF', '#7F3391', '#581F66', '#30003A']);

var breaks = scale.breaks(); // [12, 43, 123, 234, 1244]
var color = scale(52); // '#9E58AF'
var extent = scale.invertExtent('#9E58AF'); // [43, 123]
```

###Contributing

```
npm install
npm run test  # run tests
npm run build # build distributable file
```

###Thanks

This project uses the [Ckmeans](http://simplestatistics.org/docs/#ckmeans) implementation from the [https://github.com/simple-statistics/simple-statistics](simple-statistics) library–with the original algorithm written by [http://journal.r-project.org/archive/2011-2/RJournal_2011-2_Wang+Song.pdf](Haizhou Wang and Mingzhou Song)