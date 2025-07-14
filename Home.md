
# Projetos

- [[SOS Paperless]]
- [[Okumas e Chirons na Rede]]


```dataviewjs   
function getClosestPayday(year, month) {  
    let today = new Date();  
  
    let lastDay = new Date(year, month, 0);  
    let fullPayday = new Date(lastDay);

    while (fullPayday.getDay() === 0 || fullPayday.getDay() === 6) {  
        fullPayday.setDate(fullPayday.getDate() - 1);  
    }

    fullPayday.setDate(fullPayday.getDate() - 1);  
    while (fullPayday.getDay() === 0 || fullPayday.getDay() === 6) {  
        fullPayday.setDate(fullPayday.getDate() - 1);  
    }

    let halfPayday = new Date(fullPayday);  
    halfPayday.setDate(halfPayday.getDate() - 15);  
    while (halfPayday.getDay() === 0 || halfPayday.getDay() === 6) {  
        halfPayday.setDate(halfPayday.getDate() - 1);  
    }

    let nextPayday = today > halfPayday ? fullPayday : halfPayday;  
  
    return nextPayday  
}

function getMinutesDifference(date1, date2) { let diffMilliseconds = Math.abs(date2 - date1); return Math.floor(diffMilliseconds / (1000 * 60)); }

const today = moment()

let next = getClosestPayday(today.year(), today.month() + 1)  
if (next.getDay() <= (new Date()).getDay()) {  
  next = getClosestPayday(today.year(), today.month() + 2)  
}  
const minutes = getMinutesDifference(new Date(), next)

next = moment(next)

dv.header(3, "Proximo Pagamento💸 → " + moment(next).format("DD/MM/yyyy"))  
dv.header(6, `Ainda faltam ${minutes} minutos!`)

```

# Extensões
- Dataview
- Charts
- Iconize
- Git
- Excalidraw