
- Conseguir pegar quais medições são feitas em quais máquinas, se for possível

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




