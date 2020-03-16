# Getting Started

create table activos(
	
	id serial,
	nombre varchar(30),
	descripcion varchar(100),
	tipo varchar(30),
	num_serial varchar(30),
	num_interno_inventario varchar(30),
	peso decimal(4,4),
	alto decimal(4,4),
	ancho decimal(4,4),
	largo decimal(4,4),
	valor_compra double precision,
	fecha_compra date,
	fecha_baja date,
	estado_Actual varchar(50),
	color varchar(30),
	primary key(id)
	
)


create table stock_persona (
	
	id serial,
	id_activo Integer,
	nombre varchar(30),
	apellido varchar(30),
	cedula varchar(100),
	cargo varchar(20),
	primary key(id)

)


create table area (
	
	id serial,
	id_activo Integer,
	nombre_ciudad varchar(30),
	primary key(id, id_activo)

)


alter table stock_persona add constraint fk_id_activos foreign key(id_activo) references activos(id)

alter table area add constraint fk_id_act foreign key(id_activo) references activos(id).

