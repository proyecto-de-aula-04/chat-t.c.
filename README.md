
perfiles = {}

def crear_perfil():
    nombre = input("Ingrese su nombre: ")
    edad = input("Ingresa su edad: ")
    hobbys = input("Ingresa sus hobbys: ")
    carrera = input("Ingrese su carrera: ")
    telefono = input("Ingrese su numero (presione enter para omitir): ")
    if not telefono:
        telefono = "no proporcionado"
    print ('perfil creado exitosamente')
    perfiles[nombre] = {'Edad': edad, 'Hobbys': hobbys, 'Carrera': carrera, 'Teléfono': telefono}

def buscar_perfil():
    nombre = input("Ingresa el nombre del usuario a buscar: ")
    if nombre in perfiles:
        print(f"Perfil encontrado. {nombre}: {perfiles[nombre]}")
    else:
        print("Perfil no encontrado.")

def ver_perfiles():
    if perfiles:
        print("Perfiles creados:")
        for nombre, perfil in perfiles.items():
            print(f"{nombre}: {perfil}")
    else:
        print("No se han creado perfiles.")

def menu():
    while True:
        print("\n1. Crear perfil")
        print("2. Buscar perfil")
        print("3. Ver perfiles creados")
        print("4. Salir")
        
        opcion = input("Elige una opción: ")
        
        if opcion == '1':
            crear_perfil()
        elif opcion == '2':
            buscar_perfil()
        elif opcion == '3':
            ver_perfiles()
        elif opcion == '4':
            print("Saliendo del programa.")
            break
        else:
            print("Opción no válida. Por favor, intenta de nuevo.")

menu()
