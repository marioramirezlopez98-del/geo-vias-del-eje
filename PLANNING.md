## Historias de usuario


* **Como usuario**, quiero registrarme para acceder a la plataforma

* **Como usuario**, quiero iniciar sesión para acceder a la plataforma

* **Como conductor**, quiero conocer el acceso a las vías para evitar el tráfico

* **Como conductor**, quiero filtrar los reportes por tipo y fecha para tomar decisiones en el trayecto

* **Como ciudadano**, quiero reportar el estado de las calles para mejorar la movilidad

* **Como ciudadano**, quiero finalizar reportes de otros usuarios para evitar información desactualizada

## Modelo de Datos


```dbml
Table users {
  id integer [primary key]
  username varchar
  password varchar
  created_at timestamp
}


Table Reports {
  id integer [primary key]
  type varchar
  location varchar
  created_at timestamp
  solved boolean
  created_by integer
  finalized_by integer
}


Ref: Reports.created_by > users.id
Ref: Reports.finalized_by > users.id
```
