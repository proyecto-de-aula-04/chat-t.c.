perfiles = {}

def es_numero(valor):
    try:
        int (valor)
        return True
    except ValueError:
        return False 

def crear_perfil():
    nombre = input("Ingrese su nombre: ")
    edad = input("Ingresa su edad: ")
    while not es_numero(edad):
        print("ERROR: porfavor, ingrese solo numeros para la edad.")
        edad = input ("ingrese la edad:")
    pasatiempos = input("Ingresa su pasatiempo (s): ")
    carrera = input("Ingrese su carrera: ")
    telefono = input("Ingrese su numero: ")
    while not es_numero(telefono):
        print ("ERROR: por favor; ingrese solo numeros para el telefono.")
        telefono = input ("Ingrese su numero:")
    
    print ('perfil creado exitosamente')

    perfiles[nombre] = {'Edad': edad,'Pasatiempos': pasatiempos, 'Carrera': carrera, 'Teléfono': telefono}

def buscar_perfil():
    nombre = input("Ingresa el nombre del usuario a buscar: ")
    if nombre in perfiles:
        print(f"Perfil encontrado 🛎. {nombre}: {perfiles[nombre]}")
    else:
        print("Perfil no encontrado ❌.")

def ver_perfiles():
    if perfiles:
        print("Acontinuacion se mostraran todos los perfiles registrados 🌐:")
        for nombre, perfil in perfiles.items():
            print(f"{nombre}: {perfil}")
    else:
        print("No se han creado perfiles 👀.")

def menu():
    while True:
        print ("\n« BIENVENIDO A CHAT TC »")
        print("1. Crear perfil ✨")
        print("2. Buscar perfil 🔍")
        print("3. Ver perfiles creados 🌐")
        print("4. Salir 🔙")
        
        opcion = input("⟪ Elige una opción ⟫ ")
        
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
            print("Opción no válida 🚫. Por favor, intenta de nuevo .")

menu()
