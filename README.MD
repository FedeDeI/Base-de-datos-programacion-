# **MODELO DE BASE DE DATOS**
### FEDERICO NAHUEL DELGADO

- [Usuarios](#usuarios)
- [Materias](#materias)
- [Carrera](#carrera)
- [Publicacion General](#publicacionGeneral)

#

####  **USUARIOS**
```js
USUARIO{
    NOMBRE:{type:String,required:true},
    APELLIDO:{type:String,required:true},
    DNI:{type:String,required:true},
    CONTRASENIA:{type:String,required:true},
    EMAIL:{type:String,required:true},
    TIPO PERFIL[
        PERFIL[{
            ALUMNO:{type:String,required:true},
            PROFESOR:{type:String,required:true},
            ADMIN:{type:String,required:true},
        }]
    ]
    DATOSALUMNO:[
        {
            CARRERA:{type:String},
            ANALITICO:{type:String},
            CERTIFICADODOMICILIO:{type:String},
        }
    ]
    DATOSPROFESORES:[
        {
            ANALITICO:{type:String},
        }
    ]
    DATOSADMIN:[
        {
        }
    ]
}

```
####  **MATERIAS**
```js
MATERIA{
    NOMBRE:{type:String,required:true},
    PROFESOR:[
        {
            NOMBRE PROFESOR:{type: mongoose.Schema.Types.ObjectId ref: 'USUARIO'}
        }
    ],
    ANIO CURSADA:{},
    NOTAS:[
        {
            ALUMNO: {type: mongoose.Schema.Types.ObjectId,ref: 'USUARIO'},
            PARCIAL1:{type: String,require: true,},
            PARCIAL2:{type: String,require: true,},
            RECUPERATORIO:{type: String,require: flase,},
            FINAL:{type: String,require: false,},
        }
    ],
    FALTAS:[
        {
            DIA:{type: Date,},
            ALUMNOFALTA:{type: Schema.Types.ObjectId,ref: "USUARIO",},
        }
    ]
    PUBLICACION:{},
}
```

####  **CARRERA**
```js
CARRERA{
    NOMBRE:{type:String,required:true},
    ANIO:{},
    CUATRIMESTRE:{}
}
```
####  **PUBLICACION GENERAL**
```js
PUBLICACION GENERAL{},
```