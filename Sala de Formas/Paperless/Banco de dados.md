
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

- Querry do power bi: 
	- SELECT * FROM Machine m
        INNER JOIN Request r ON m.id = r.IdMachine
        INNER JOIN PartNumber s ON r.IdPartNumber = s.id
		INNER JOIN Card c ON r.IdCard = c.id
        WHERE m.LocationDescription LIKE '%CRIN%'
        ORDER BY r.Created DESC


- Querry do power bi (2.0): 
	SELECT * FROM Machine m
	INNER JOIN Request r ON m.id = r.IdMachine
	INNER JOIN PartNumber s ON r.IdPartNumber = s.id
	INNER JOIN Card c ON r.IdCard = c.id
	INNER JOIN MeasurePlan mp ON c.IdMeasurePlan = mp.id
	INNER JOIN MeasureRoom mr ON mp.IdMeasureRoom = mr.id
	WHERE mr.Name LIKE '%ct201%'
	ORDER BY r.Created DESC;



- Querry do power bi (que pega os dados das peças medidas na bancada tambem): 
		SELECT * FROM Machine m
        INNER JOIN Request r ON m.id = r.IdMachine
        INNER JOIN PartNumber s ON r.IdPartNumber = s.id
		INNER JOIN Card c ON r.IdCard = c.id
		INNER JOIN MeasurePlan mp ON c.IdMeasurePlan = mp.id
		INNER JOIN MeasureRoom mr ON mp.IdMeasureRoom = mr.id
        WHERE Mr.Name LIKE '%201%'
        ORDER BY r.Created DESC


Querry do power bi tabela 2 (para pegar o grupo de medição das maquinas da sala de formas ) 
  SELECT * FROM Machine m
        INNER JOIN MeasureEquipment me ON m.Inventory = me.Inventory
		INNER JOIN MeasureGroup mg ON mg.Id = me.IdMeasureGroup
		INNER JOIN Characteristic c ON c.IdMeasureGroup = mg.id
        WHERE m.LocationDescription LIKE '%201%'
   
    