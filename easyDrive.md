```mermaid
classDiagram
    class Users {
        -Long id
        -String username
        -String password
        -Boolean enabled
        -List~Role~ roles
        +getId() Long
        +setId(Long)
        +getUsername() String
        +setUsername(String)
        +getPassword() String
        +setPassword(String)
        +getEnabled() Boolean
        +setEnabled(Boolean)
        +getRoles() List~Role~
        +setRoles(List~Role~)
    }

    class Telefonos {
        -int IDTelefono
        -String TipoDeTelefono
        -String NumeroTelefono
        -String AnexoEscuelas
        -Users user
        -Escuelas esc
        -CentrosMedicos centros
        +getIDTelefono() int
        +setIDTelefono(int)
        +getTipoDeTelefono() String
        +setTipoDeTelefono(String)
        +getNumeroTelefono() String
        +setNumeroTelefono(String)
        +getAnexoEscuelas() String
        +setAnexoEscuelas(String)
        +getUser() Users
        +setUser(Users)
        +getEsc() Escuelas
        +setEsc(Escuelas)
        +getCentros() CentrosMedicos
        +setCentros(CentrosMedicos)
    }

    class Servicio {
        -int IDServicio
        -String NombreServicio
        -String Descripcion
        -Float Precio
        +getIDServicio() int
        +setIDServicio(int)
        +getNombreServicio() String
        +setNombreServicio(String)
        +getDescripcion() String
        +setDescripcion(String)
        +getPrecio() Float
        +setPrecio(Float)
    }

    class Role {
        -Long id
        -String rol
        -Users user
        +getId() Long
        +setId(Long)
        +getRol() String
        +setRol(String)
        +getUser() Users
        +setUser(Users)
    }

    class Reservas {
        -int IDReserva
        -LocalDate FechaReserva
        -String EstadoReserva
        -Users user
        -Escuelas esc
        -CentrosMedicos centros
        -Servicio ser
        -Promocion prom
        +getIDReserva() int
        +setIDReserva(int)
        +getFechaReserva() LocalDate
        +setFechaReserva(LocalDate)
        +getEstadoReserva() String
        +setEstadoReserva(String)
        +getUser() Users
        +setUser(Users)
        +getEsc() Escuelas
        +setEsc(Escuelas)
        +getCentros() CentrosMedicos
        +setCentros(CentrosMedicos)
        +getSer() Servicio
        +setSer(Servicio)
        +getProm() Promocion
        +setProm(Promocion)
    }

    class Resenias {
        -int IDResenia
        -float Calificacion
        -String Comentario
        -LocalDate FechaResenia
        -Users user
        -Escuelas esc
        -CentrosMedicos centros
        +getIDResenia() int
        +setIDResenia(int)
        +getCalificacion() float
        +setCalificacion(float)
        +getComentario() String
        +setComentario(String)
        +getFechaResenia() LocalDate
        +setFechaResenia(LocalDate)
        +getUser() Users
        +setUser(Users)
        +getEsc() Escuelas
        +setEsc(Escuelas)
        +getCentros() CentrosMedicos
        +setCentros(CentrosMedicos)
    }

    class Promocion {
        -int IDPromocion
        -String NombrePromocion
        -String Descripcion
        -int Descuento
        -LocalDate FechaInicio
        -LocalDate FechaFin
        +getIDPromocion() int
        +setIDPromocion(int)
        +getNombrePromocion() String
        +setNombrePromocion(String)
        +getDescripcion() String
        +setDescripcion(String)
        +getDescuento() int
        +setDescuento(int)
        +getFechaInicio() LocalDate
        +setFechaInicio(LocalDate)
        +getFechaFin() LocalDate
        +setFechaFin(LocalDate)
    }

    class Pagos {
        -int IDPago
        -LocalDate FechaPago
        -Reservas res
        -MetodoPago metodo
        +getIDPago() int
        +setIDPago(int)
        +getFechaPago() LocalDate
        +setFechaPago(LocalDate)
        +getRes() Reservas
        +setRes(Reservas)
        +getMetodo() MetodoPago
        +setMetodo(MetodoPago)
    }

    class Notificaciones {
        -int IDNotificacion
        -String Titulo
        -String Mensaje
        -LocalDate FechaNotificacion
        -Users user
        +getIDNotificacion() int
        +setIDNotificacion(int)
        +getTitulo() String
        +setTitulo(String)
        +getMensaje() String
        +setMensaje(String)
        +getFechaNotificacion() LocalDate
        +setFechaNotificacion(LocalDate)
        +getUser() Users
        +setUser(Users)
    }

    class MetodoPago {
        -int IDMetodo
        -String MetodoPago
        +getIDMetodo() int
        +setIDMetodo(int)
        +getMetodoPago() String
        +setMetodoPago(String)
    }

    class Escuelas {
        -int IDEscuela
        -String nombre
        -Long Ruc
        -Promocion prom
        +getIDEscuela() int
        +setIDEscuela(int)
        +getNombre() String
        +setNombre(String)
        +getRuc() Long
        +setRuc(Long)
        +getProm() Promocion
        +setProm(Promocion)
    }

    class Direcciones {
        -int IDdireccion
        -String Calle
        -String Ciudad
        -String EstadProvincia
        -int CodigoPostal
        -String Pais
        -Long Latitud
        -Long Longitud
        -Users user
        -Escuelas esc
        +getIDdireccion() int
        +setIDdireccion(int)
        +getCalle() String
        +setCalle(String)
        +getCiudad() String
        +setCiudad(String)
        +getEstadProvincia() String
        +setEstadProvincia(String)
        +getCodigoPostal() int
        +setCodigoPostal(int)
        +getPais() String
        +setPais(String)
        +getLatitud() Long
        +setLatitud(Long)
        +getLongitud() Long
        +setLongitud(Long)
        +getUser() Users
        +setUser(Users)
        +getEsc() Escuelas
        +setEsc(Escuelas)
    }

    class CentrosMedicos {
        -int IDCentro
        -String Nombre
        -long RUC
        +getIDCentro() int
        +setIDCentro(int)
        +getNombre() String
        +setNombre(String)
        +getRUC() long
        +setRUC(long)
    }

    class Calendario {
        -int IDCalendario
        -LocalDate FechaSincronizacion
        -Reservas res
        +getIDCalendario() int
        +setIDCalendario(int)
        +getFechaSincronizacion() LocalDate
        +setFechaSincronizacion(LocalDate)
        +getRes() Reservas
        +setRes(Reservas)
    }

    Users "1" -- "0..*" Role : has
    Users "1" -- "0..*" Telefonos : has
    Users "1" -- "0..*" Reservas : makes
    Users "1" -- "0..*" Resenias : writes
    Users "1" -- "0..*" Notificaciones : receives
    Users "1" -- "0..*" Direcciones : has

    Escuelas "1" -- "0..*" Telefonos : has
    Escuelas "1" -- "0..*" Reservas : involved in
    Escuelas "1" -- "0..*" Resenias : receives
    Escuelas "1" -- "0..*" Direcciones : has
    Escuelas "0..*" -- "1" Promocion : has

    CentrosMedicos "1" -- "0..*" Telefonos : has
    CentrosMedicos "1" -- "0..*" Reservas : involved in
    CentrosMedicos "1" -- "0..*" Resenias : receives

    Servicio "1" -- "0..*" Reservas : included in

    Promocion "1" -- "0..*" Reservas : applied to

    Reservas "1" -- "0..*" Pagos : has
    Reservas "1" -- "1" Calendario : synced with

    MetodoPago "1" -- "0..*" Pagos : used in