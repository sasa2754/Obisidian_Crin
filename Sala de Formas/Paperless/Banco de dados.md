
# Conexão com o banco

Banco de Dados Server: CT0BD05 (10.21.157.91)   
DataBase: Paperless   
User: Paperless_50970367_TEF41.Read   
Password:mhJLPwpLwq41

# Tabelas importantes

- CharacteristicDictionary
- Characteristic
- Operation


# Querys importantes

- Para pegar todas as máquinas que tem na sala de formas do crin: 
    -  select * from Machine where LocationDescription like '%201 Sala de formas%'

- Para pegar as máquinas do marsurf, o número do inventário, o que elas fazem e onde estão
    - select  
        m.Inventory,  
        m.Alias,  
        o.Number,  
        o.Description,  
        m.Location,  
        m.LocationDescription  
        from OperationMachine om  
        inner join Machine m on om.IdMachine = m.Id  
        inner join Operation o on om.IdOperation = o.Id  
        where Alias like '%MarSurf%'

- Caracteristicas medidas em cada part number
    - SELECT  
        cd.FileCharacteristic,  
        cd.Program,  
        c.Name,  
        c.Description  
        FROM CharacteristicDictionary cd  
        INNER JOIN Characteristic c ON cd.IdCharacteristic = c.Id  
        WHERE cd.Program LIKE '%Isuzu%1095%';



- Pegar o chekin do crin
	- select
		*
		from Machine m
		inner join Request r on m.id = r.IdMachine
		where m.LocationDescription like '%CRIN%'
		order by r.Created desc

- Pegar a criação do terminal de chck-in
	- Select
		t.Created as "Data de criação checkin",
		t.Deleted as "Deletar checkin?",
		m.Description as "Sala de formas",
		m.IsCheckinRequired,
		m.Modified
		from TerminalCheckIn t
		inner join MeasureRoom m
		on m.Id like t.IdMeasureRoom
		where m.Description like '%201%'

