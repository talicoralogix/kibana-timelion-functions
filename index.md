# Kibana Timelion Functions

| Function | Syntax |
| --- | --- |
| .abs() | `.es(*).abs()` |
| .add() or .plus() or .sum() | `.aggregate()	.es(*).add(term=.es(..))` or `.es(*).add(term=2000)` |
| .aggregate()	 | `.es(*).aggregate(function=avg)` |
| .bars() | `.es(*).bars(width=0.5,stack=yes)` |
| .color() | `.es(*).color(color=#c6c6c6)` or `.es(*).color(color=grey)` |
| .cusum() | `.es(*).cusum(base=0)` |
| .derivative() | `.es(*).derivative()` |
| .divide() | `.es(*).divide(divisor=.es(..))` or `.es(*).divide(divisor=2000)` |
| .es() | `.es(q=...,metric=...,split=...,index=...,timefield=...,kibana=...,offset=...,fit=...)`    </br> Note: You may use any of the arguments including all together, non are mandatory. E.g. .es() or .es(*) will give you all the data |
| .es(q) | `.es(q="status_code:500 AND http_method:get")` |
| .es(metric)	 | `.es(metric=sum:bytes_sent.numeric)` or `.es(metric="percentiles:bytes_sent.numeric:1,25,50,75,95,99")` |
| .es(split) | `.es(split=hostname.keyword:10)` |
| .es(index) | `.es(index="your index name",split=hostname.keyword:5)` |
| .es(timefield) | `.es(timefield=coralogix.timestamp)` |
| .es(kibana) | `.es(kibana=true)` |
| .es(offset) | `.es(offset=-1w)` or `.es(offset=timerange:-3)` |
| .es(fit) | `.es(fit=scale)` |
| .fit() | `.es(*).fit(mode=carry)` |
| .hide() | `.es(*).hide(hide=true)` |
| .holt() | `.es(*).holt(alpha=...,beta=...,gamma=...,season=...,sample=...)` |
| .holt(alpha) | `.es(*).holt(alpha=0.4)` |
| .holt(beta) | `.es(*).holt(beta=0.7)` |
| .holt(gamma) | `.es(*).holt(gamma=0.9,season=1w,sample=2)` |
| .holt(season) | `.es(*).holt(gamma=0.9,season=1w,sample=2)` |
| .holt(sample) | `.es(*).holt(gamma=0.9,season=1w,sample=2)` |
| .if() | `.es(*).if(operator=...,if=...,then=...,else=...)` |
| .if(operator) | `.es(*).if(operator=lt,if=5000,then=0)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...))` |
| .if(if) | `.es(*).if(operator=lt,if=5000,then=0)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...))` |
| .if(then) | `.es(*).if(operator=lt,if=5000,then=0)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...))` |
| .if(else) | `.es(*).if(operator=lt,if=5000,then=0,else=10000)` or `.es(*).if(operator=lt,if=.es(...),then=.es(...),else=.es(...))` |
| .label() | `.es(split=level.keyword:5).label(regex=".*keyword:([a-zA-Z]+).*",label="$1")` |
| .legend() | `.es(*).legend(position=...,columns=...,showTime=...,timeFormat=...)` |
| .legend(position) | `.es(split=level.keyword:5).legend(position=ne)` |
| .legend(columns) | `es(split=level.keyword:5).legend(position=ne,columns=4)` |
| .legend(showTime) | `.es(split=level.keyword:5).legend(position=ne,columns=4,showTime=true)` |
| .legend(timeFormat) | `.es(split=level.keyword:5).legend(position=ne,columns=4,showTime=true,timeFormat="dddd, MMMM Do YYYY, h:mm:ss a")`       [momentjs time formats guide](https://momentjs.com/docs/#/displaying/format/) |
| .lines() | `.es(*).lines(fill=...,width=...,show=...,stack=...,steps=...)` |
| .lines(fill) | `.es(*).lines(fill=1.2)` |
| .lines(width) | `.es(*).lines(fill=1.2,width=0.2)` |
| .lines(show) | `.es(*).lines(fill=1.2,width=0.2,show=null)` |
| .lines(stack) | `.es(split=level.keyword:5).lines(fill=1.2,width=0.2,show=null,stack=true)` |
| .lines(steps) | `.es(split=level.keyword:5).lines(fill=1.2,width=0.2,show=null,stack=true,steps=true)` |
| .log() | `.es(*).log(base=2)` |
| .max() | `.es(*).max(value=100000)` or `.es(*).max(value=.es(...))` |
| .min() | `.es(*).min(value=100000)` or `.es(*).min(value=.es(...))` |
| .multiply() | `.es(*).multiply(multiplier=2)` or `.es(*).multiply(multiplier=.es(...))` |
| .mvavg() | `.es(*).mvavg(position=center,window=1h)` or `.es(*).mvavg(position=center,window=10)` |
| .mvstd() | `.es(*).mvstd(position=center,window=10)` |
| .points() | `.es(*).points(fill=1.4,fillColor=navy,radius=4.1,show=true,symbol=diamond,weight=0.9)` |
| .precision() | `.es(*).precision(precision=3)` |
| .range() | `.es(*).range(min=0,max=100)` |
| .scale_interval() | `.es(*).scale_interval(interval=1s)` |
| .static() or .value() | `.static(value=200,label="static line")` or `.static(value="200:300:400:100",label="static line")` |
| .subtract() | `.es(*).subtract(term=.es(..))` or `.es(*).subtract(term=200)` |
| .title() | `.es(*).title(title="my title")` |
| .trend() | `.es(*).trend(mode=linear,start=10,end=-10)` |
| .trim() | `.es(*).trim(start=4,end=4)` |
| .yaxis() | `.es(*).yaxis(color=...,label=...,show=...,max=...,min=...,position=...,tickDecimals=...,units=...,yaxis=...)` |
| .yaxis(color) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(label) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(max) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(min) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(position) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(tickDecimals) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(units) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
| .yaxis(yaxis) | `.es(*).yaxis(color=blue,position=left,label=count,min=100,max=500,tickDecimals=2,units=bytes,yaxis=1)` |
