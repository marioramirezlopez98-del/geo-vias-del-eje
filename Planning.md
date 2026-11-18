Historias de usuario


Como usuario
Quiero registrarme
Para acceder a la plataforma

Como usuario
Quiero iniciar sesión
Para acceder a la plataforma

Como conductor
Quiero conocer el acceso a las vías
Para evitar el tráfico

Como conductor
Quiero filtrar los reportes por tipo y fecha
Para tomar decisiones en el trayecto

Como ciudadano
Quiero reportar el estado de las calles
Para mejorar la movilidad

Como ciudadano
Quiero finalizar reportes de otros usuarios
Para evitar información desactualizada



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
