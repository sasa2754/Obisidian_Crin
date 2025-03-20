- #Acíclico André
	- Maior dificuldade: O registro de acompanhamento de lavadora é em papel, o que é bem ruim para todo o processo. Além de ter reclamado que o paperless exige muito tempo para registrar os cartões da sala de formas e é mais rápido anotar os dados na mão ou no Excel
- #Ajustador Erivaldo
	- Não tem uma maior dificuldade
- #Operador Vincícius
	- Maior dificuldade: Reclamou do registro de acompanhamento de lavadora também, mas a principal reclamação foi que os IT's Digitais não abrem já faz um tempo
- #Operador Bruno
	- Maior dificuldade: As ITs Digitais não estão abrindo faz tempo


| Cargo     | Nome     | Problemas         |
| --------- | -------- | ----------------- |
| Acíclico  | André    | #Paperless #Papel |
| Ajustador | Erivaldo | #Nada             |
| Operador  | Vinícius | #ITDigital #Papel |
```dataviewjs
const file = dv.page('')
console.log(file.file.lists)
```

<table id="tableUsinFinal">
  <thead>
    <tr>
      <th>Cargo</th>
      <th>Nome</th>
      <th>Problemas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Acíclico</td>
      <td>André</td>
      <td>#Paperless #Papel</td>
    </tr>
    <tr>
      <td>Ajustador</td>
      <td>Erivaldo</td>
      <td>#Nada</td>
    </tr>
    <tr>
      <td>Operador</td>
      <td>Vinícius</td>
      <td>#ITDigital #Papel</td>
    </tr>
  </tbody>
</table>

```dataviewjs

const data = getElementById("tableUsinFinal")

console.log(data)
```
>>>>>>> origin/main
