# parcial-final1
#ejercicio 1
clientes = {}

while True:
    nombre_cliente = input("Ingrese el nombre del cliente (o 'salir' para terminar): ")

    if nombre_cliente.lower() == 'salir':
        break

    compro_varita = input(f"¿{nombre_cliente} compró una varita? (Sí/No): ").lower()

    if compro_varita == 'sí':
        print("Opciones de varitas: 1. Varita de Saúco, 2. Varita de Espino, 3. Varita de Sauce, 4. Varita de Acebo")
        opcion_varita = int(input(f"Seleccione la varita para {nombre_cliente} (1-4): "))

        varitas_disponibles = ["Varita de Saúco", "Varita de Espino", "Varita de Sauce", "Varita de Acebo"]

        if opcion_varita in range(1, 5):
            varita_elegida = varitas_disponibles[opcion_varita - 1]
            clientes[nombre_cliente] = varita_elegida
            print(f"{nombre_cliente} compró una {varita_elegida}")
        else:
            print("Opción de varita inválida.")
    else:
        clientes[nombre_cliente] = "No compró varita"
        print(f"{nombre_cliente} no compró una varita.")

print("Registro de clientes y varitas compradas:")
for cliente, varita in clientes.items():
    print(f"{cliente}: {varita}")
#ejercicio 2
texto = input("Ingrese un texto: ")


palabras = texto.split()
contador_alexa = palabras.count('Alexa')

if contador_alexa == 1:
    print("¡Hola, soy tu asistente virtual!")
elif contador_alexa > 1:
    print("Tranquilo, solo di mi nombre una vez.")
else:
    print("No mencionaste mi nombre.")

#ejercicio 3

lecturas = [8, 25, 38, 42, 10, 9, 40, 41, 12, 39]

lecturas_fuera_rango = 0  

for lectura in lecturas:
    if lectura < 10 or lectura > 40:
        lecturas_fuera_rango += 1

porcentaje_error = (lecturas_fuera_rango / len(lecturas)) * 100

print(f"Porcentaje de lecturas fuera de rango: {porcentaje_error:.2f}%")

#desafio magico

gryffindor_score = 0
slytherin_score = 0


num_eventos = int(input("Ingresa el número de eventos en el partido de Quidditch: "))


for _ in range(num_eventos):
    evento = input("Ingresa un evento (goal/snitch/foul): ")

    if evento == "goal":
        equipo = input("¿Qué equipo anotó (Gryffindor o Slytherin): ")
        if equipo == "Gryffindor":
            gryffindor_score += 10
        elif equipo == "Slytherin":
            slytherin_score += 10
    elif evento == "snitch":
        equipo = input("¿Qué equipo atrapó la Snitch (Gryffindor o Slytherin): ")
        if equipo == "Gryffindor":
            gryffindor_score += 150
        elif equipo == "Slytherin":
            slytherin_score += 150
    elif evento == "foul":
        equipo = input("¿Qué equipo cometió una falta (Gryffindor o Slytherin): ")
        if equipo == "Gryffindor":
            gryffindor_score -= 30
        elif equipo == "Slytherin":
            slytherin_score -= 30


print(f"Gryffindor: {gryffindor_score} puntos")
print(f"Slytherin: {slytherin_score} puntos")


if gryffindor_score > slytherin_score:
    print("¡Gryffindor gana!")
elif slytherin_score > gryffindor_score:
    print("¡Slytherin gana!")
else:
    print("¡Es un empate!")
