# Kibana Timelion Functions

| Function | Arguments | Syntax |
| --- | --- | --- |
| .abs() | not accepting any arguments | `.es(*).abs()` |
| .add() or .plus() or .sum() | term<br/>Accepted Types: seriesList, number | `.aggregate()	.es(*).add(term=.es(..))` or `.es(*).add(term=2000)` |
| .aggregate()	 | function<br/>Accepted Types: string<br/>Available functions: avg, cardinality, min, max, last, first, sum | `.es(*).aggregate(function=avg)` |
| .bars() | width<br/>Accepted Types: number, null  stack  Accepted Types: boolean, null | `.es(*).bars(width=0.5,stack=yes)` |
| .color() | color<br/>Accepted Types: string<br/>Colors of series, as hex, e.g., #c6c6c6 is light grey. If you specify multiple colors, and have multiple series, you will get a gradient, e.g., “#00B1CC:#00FF94:#FF3A39:#CC1A6F” | `.es(*).color(color=#c6c6c6)` or `.es(*).color(color=grey)` |
| .cusum() | base<br/>Accepted Types: number | `.es(*).cusum(base=0)` |
| .derivative() | not accepting any arguments | `.es(*).derivative()` |
| .divide() | divisor<br/>Accepted Types: seriesList, number | `.es(*).divide(divisor=.es(..))` or `.es(*).divide(divisor=2000)` |
| .es() | q, metric, split, index, timefield, kibana, offset, fit | `.es(q=...,metric=...,split=...,index=...,timefield=...,kibana=...,offset=...,fit=...)`  <br/>Note: You may use any of the arguments including all together, non are mandatory. E.g. .es() or .es(*) will give you all the data |
| .es(q) | q<br/>Accepted Types: string, null | `.es(q="status_code:500 AND http_method:get")` |
| .es(metric)	 | metric<br/>Accepted Types: string, null | `.es(metric=sum:bytes_sent.numeric)` or `.es(metric="percentiles:bytes_sent.numeric:1,25,50,75,95,99")` |
| .es(split) | split<br/>Accepted Types: string, null | `.es(split=hostname.keyword:10)` |
| .es(index) | 	index<br/>Accepted Types: string, null | `.es(index="your index name",split=hostname.keyword:5)` |
| .es(timefield) | timefield<br/>Accepted Types: string, null | `.es(timefield=coralogix.timestamp)` |
| .es(kibana) | kibana<br/>Accepted Types: boolean, null | `.es(kibana=true)` |
| .es(offset) | offset<br/>Accepted Types: string, null| `.es(offset=-1w)` or `.es(offset=timerange:-3)` |
| .es(fit) | fit<br/>Accepted Types: string, null<br/>Available: average, carry, nearest, none, scale | `.es(fit=scale)` |
| .fit() | mode<br/>Accepted Types: string<br/>The algorithm to use for fitting the series to the target. One of: average, carry, nearest, none, scale | `.es(*).fit(mode=carry)` |
| .hide() | hide<br/>Accepted Types: boolean, null | `.es(*).hide(hide=true)` |
| .holt() | alpha, beta, gamma, season, sample | `.es(*).holt(alpha=...,beta=...,gamma=...,season=...,sample=...)` |
| .holt(alpha) | alpha<br/>Accepted Types: number | `.es(*).holt(alpha=0.4)` |
| .holt(beta) | beta<br/>Accepted Types: number | `.es(*).holt(beta=0.7)` |
| .holt(gamma) | gamma<br/>Accepted Types: number | `.es(*).holt(gamma=0.9,season=1w,sample=2)` |
| .holt(season) | season<br/>Accepted Types: string | `.es(*).holt(gamma=0.9,season=1w,sample=2)` |
| .holt(sample) | sample<br/>Accepted Types: number, null | `.es(*).holt(gamma=0.9,season=1w,sample=2)` |
| .if() | operator, if, then, else (else is optional) | `.es(*).if(operator=...,if=...,then=...,else=...)` |
| .if(operator) | operator<br/>Accepted Types: string | `.es(*).if(operator=lt,if=5000,then=0)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...))` |
| .if(if) | if<br/>Accepted Types: number, seriesList, null | `.es(*).if(operator=lt,if=5000,then=0)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...))` |
| .if(then) | then<br/>Accepted Types: number, seriesList, null | `.es(*).if(operator=lt,if=5000,then=0)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...))` |
| .if(else) | else<br/>Accepted Types: number, seriesList, null | `.es(*).if(operator=lt,if=5000,then=0,else=10000)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...),else=.es(...))` |
| .label() | label<br/>Accepted Types: string<br/>Legend value for series. You can use $1, $2, etc, in the string to match up with the regex capture groups<br/>regex<br/>Accepted Types: string, null<br/>A regex with capture group support | `.es(split=level.keyword:5).label(regex=".*keyword:([a-zA-Z]+).*",label="$1")` |
| .legend() | position, columns, showTime, timeFormat | `.es(*).legend(position=...,columns=...,showTime=...,timeFormat=...)` |
| .legend(position) | position<br/>Accepted Types: string, boolean, null | `.es(split=level.keyword:5).legend(position=ne)` |
| .legend(columns) | columns<br/>Accepted Types: number, null | `es(split=level.keyword:5).legend(position=ne,columns=4)` |
| .legend(showTime) | showTime<br/>Accepted Types: boolean | `.es(split=level.keyword:5).legend(position=ne,columns=4,showTime=true)` |
| .legend(timeFormat) | timeFormat<br/>Accepted Types: string | `.es(split=level.keyword:5).legend(position=ne,columns=4,showTime=true,timeFormat="dddd, MMMM Do YYYY, h:mm:ss a")`<br/>[momentjs time formats guide](https://momentjs.com/docs/#/displaying/format/) |
| .lines() | fill, width, show, stack, steps | `.es(*).lines(fill=...,width=...,show=...,stack=...,steps=...)` |
| .lines(fill) | fill<br/>Accepted Types: number, null | `.es(*).lines(fill=1.2)` |
| .lines(width) | width<br/>Accepted Types: number, null | `.es(*).lines(fill=1.2,width=0.2)` |
| .lines(show) | show<br/>Accepted Types: number, boolean, null | `.es(*).lines(fill=1.2,width=0.2,show=null)` |
| .lines(stack) | stack<br/>Accepted Types: boolean, null | `.es(split=level.keyword:5).lines(fill=1.2,width=0.2,show=null,stack=true)` |
| .lines(steps) | steps<br/>Accepted Types: number, boolean, null | `.es(split=level.keyword:5).lines(fill=1.2,width=0.2,show=null,stack=true,steps=true)` |
| .log() | base<br/>Accepted Types: number | `.es(*).log(base=2)` |
| .max() | value<br/>Accepted Types: seriesList, number<br/>Sets the point to whichever is higher, the existing value, or the one passed. If passing a seriesList it must contain exactly 1 series. | `.es(*).max(value=100000)` or `.es(*).max(value=.es(...))` |
| .min() | value<br/>Accepted Types: seriesList, number<br/>Sets the point to whichever is lower, the existing value, or the one passed. If passing a seriesList it must contain exactly 1 series. | `.es(*).min(value=100000)` or `.es(*).min(value=.es(...))` |
| .multiply() | multiplier<br/>Accepted Types: seriesList, number | `.es(*).multiply(multiplier=2)` or `.es(*).multiply(multiplier=.es(...))` |
| .mvavg() | window<br/>Accepted Types: string, number<br/>Number of points, or a date math expression (e.g. 1d, 1m) to average over. If a date math expression is specified, the function will get as close as possible given the current select interval. If the date math expression is not evenly divisible by the interval the results may appear abnormal.<br/>position<br/>Accepted Types: string, null<br/>Position of the averaged points relative to the result time. One of: left, right, center | `.es(*).mvavg(position=center,window=1h)` or `.es(*).mvavg(position=center,window=10)` |
| .mvstd() | window<br/>Accepted Types: number<br/>Number of points to compute the standard deviation over.<br/>position<br/>Accepted Types: string, null<br/>Position of the window slice relative to the result time. Options are left, right, center. Default: left. | `.es(*).mvstd(position=center,window=10)` |
| .points() | fill<br/>Accepted Types: number, null<br/>Number between 0 and 10 representing opacity of fill.<br/>fillColor<br/>Accepted Types: string, null<br/>Color with which to fill point.<br/>radius<br/>Accepted Types: number, null<br/>Size of points.<br/>show<br/>Accepted Types: boolean, null<br/>Show points or not.<br/>symbol<br/>Accepted Types: string, null<br/>Point symbol. One of: triangle, cross, square, diamond, circle.<br/>weight<br/>Accepted Types: number, null<br/>Thickness of line around point. | `.es(*).points(fill=1.4,fillColor=navy,radius=4.1,show=true,symbol=diamond,weight=0.9)` |
| .precision() | precision<br/>Accepted Types: number | `.es(*).precision(precision=3)` |
| .range() | max, min<br/>Accepted Types: number | `.es(*).range(min=0,max=100)` |
| .scale_interval() | interval<br/>Accepted Types: string<br/>The new interval in date math notation, e.g., 1s for 1 second. 1m, 5m, 1w, 1M, 1y, etc. | `.es(*).scale_interval(interval=1s)` |
| .static() or .value() | value<br/>Accepted Types: number, string<br/>The single value to display, you can also pass several values and it will interpolate them evenly across your time range.<br/>label<br/>Accepted Types: string, null | `.static(value=200,label="static line")` or `.static(value="200:300:400:100",label="static line")` |
| .subtract() | term<br/>Accepted Types: seriesList, number | `.es(*).subtract(term=.es(..))` or `.es(*).subtract(term=200)` |
| .title() | title<br/>Accepted Types: string, null | `.es(*).title(title="my title")` |
| .trend() | mode<br/>Accepted Types: string<br/>The algorithm to use for generating the trend line. One of: linear, log.<br/>start<br/>Accepted Types: number, null<br/>end<br/>Accepted Types: number, null<br/>Where to start/stop calculating from the beginning or end. For example, -10 would start/stop calculating 10 points from the end, +15 would start/stop 15 points from the beginning. Default: 0. | `.es(*).trend(mode=linear,start=10,end=-10)` |
| .trim() | start<br/>Accepted Types: number, null<br/>end<br/>Accepted Types: number, null<br/>Buckets to trim from the beginning/end of the series. Default: 1 | `.es(*).trim(start=4,end=4)` |
| .yaxis() | color, label, max, min, position, tickDecimals, units, yaxis | `.es(*).yaxis(color=...,label=...,show=...,max=...,min=...,position=...,tickDecimals=...,units=...,yaxis=...)` |
| .yaxis(color) | color<br/>Accepted Types: string, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(label) | label<br/>Accepted Types: string, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(max) | max<br/>Accepted Types: number, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(min) | min<br/>Accepted Types: number, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(position) | position<br/>Accepted Types: string, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(tickDecimals) | tickDecimals<br/>Accepted Types: number, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(units) | units<br/>Accepted Types: string, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(yaxis) | yaxis<br/>Accepted Types: number, null | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
