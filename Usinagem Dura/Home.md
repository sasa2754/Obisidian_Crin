[[Usinagem Dura/Avaliação das Pessoas]]

Anote algo, [[crie um link]], ou tente [o Importer](https://help.obsidian.md/Plugins/Importer)!

# Importante
- Aprender o que é o caderno de liberação das máquinas
- Os manutentores precisam alimentar os dados dos sistemas, mas eles estão sempre ocupados para isso
- As vezes os funcionários tem certa dificuldade em encontrar as informações nos sistemas
- Uma dificuldade é ter que ficar carregando vários papeis por não poder carregar o computador, uma sugestão é ter algum tipo de totem em lugares estratégicos.
- Fazer um sistema pro planejamento dos exóticos com base no excel deles
- OEE no cockpit tem um problema de sempre puxar a data errada e também abaixa sozinho por ter algumas máquinas que não estão rodando, então tem que selecionar as máquinas certas
- É um problema ter vários sistemas e as pessoas terem que ficar procurando as informações entre esses sistemas

# Principais Ferramentas
- Daily Cockpit
- Pull System
- Process Management
- ESMC
- IScrap
- Tool Management


```dataviewjs
let pages = dv.pages()


dv.header(3, "Paginas")


%% dv.list(pages) %%
```


```dataviewjs
const pages = dv.pages()
const testNames = pages.map(p => p.file.name).values
const testMarks = pages.map(p => p.tags.count)

const chartData = {
    type: 'bar',
    data: {
        labels: testNames,
        datasets: [{
            label: 'Mark',
            data: testMarks,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1,
        }]
    }
}

window.renderChart(chartData, this.container)
```
