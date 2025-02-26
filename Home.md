# Extensões
- Dataview
- Charts
- Iconize
- Git



```dataviewjs
const data = dv.pages('')


const dict = []

data.forEach(x => {
	dict.push({title: x.file.name, tags: x.file.tags.length})
});

const filtered = dict.filter(x => x.tags > 0)


const chartData = {
	type: 'bar',
	data: {
		labels: filtered.map(x => x.title),
		datasets: [{
			label: "Tags Count",
			data: filtered.map(x => x.tags)
		}]
	}
}

window.renderChart(chartData, this.container)
```

