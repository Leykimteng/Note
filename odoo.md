#### Basic Odoo
Button represent the function   
each button can contain more than one function  

MOdel represent class in web server and table in database

Each data run on each port

View of Odoo

Attributes (Rule)
Function (Base On logic)

odoo migration is auto and if you insert any change can chane by update the odoo

----
#### 16/08/2018

client →(CruD) Database Server  

DBMS

* Virtual Environment (Enviroment in the each project)  
* Native Environment  (Enviroment in the OS)  

Focus on Self:Obj pointer and write create

Overrudeing in python odoo  

# self = id
is used for identify corrent data
>___Note___  
All self of crud have ID except create function 
 
#### self.env
it use the form of json to identify data not the form of array  
````
class T2 (model.model): 
    sfjslkdfj
    
    
class T1 (model.model): 
    name = fiield.char("    ")
    def confirm(self)
    vars = {'age' : self.age +1}
    t2.obj = self.env['m.t2']        // declare obj from class t2
                                     // .env = .pool.get
````
cr u id imbanded in decorator   
example   
@apt.multi  decorator


vals={'age'=0,'state'='cancel'}
self.write(vals)    

same as   

self.age =0  
self.state = 'cancel'  

#### browse
browse make it have id for making sure  
stock.obj=self.env['stock.move']  
stock.obj.ids = stock.obj.browse([1])  

syntax   
`browse([domain])`  
domain: [ ids ]  

stock_obj_ids.write(vals)  

