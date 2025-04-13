# Reyne´s Morse
Código python que convierte texto a código Morse utilizando una letra como base.

Text to morse code using my own style.
 
````
def texto_a_morse(texto, caracter):
    # Diccionario de código Morse
    morse_dict = {
        'A': '.-', 'B': '-...', 'C': '-.-.', 'D': '-..', 'E': '.', 'F': '..-.', 
        'G': '--.', 'H': '....', 'I': '..', 'J': '.---', 'K': '-.-', 'L': '.-..', 
        'M': '--', 'N': '-.', 'O': '---', 'P': '.--.', 'Q': '--.-', 'R': '.-.', 
        'S': '...', 'T': '-', 'U': '..-', 'V': '...-', 'W': '.--', 'X': '-..-', 
        'Y': '-.--', 'Z': '--..', '0': '-----', '1': '.----', '2': '..---', 
        '3': '...--', '4': '....-', '5': '.....', '6': '-....', '7': '--...', 
        '8': '---..', '9': '----.', ' ': '/'
    }
    
    resultado = []
    
    for letra in texto.upper():
        if letra in morse_dict:
            # Reemplazar los puntos y rayas con el caracter
            morse = morse_dict[letra].replace('.', caracter).replace('-', caracter*2)
            resultado.append(morse)
        else:
            # Si el carácter no está en el diccionario, se omite
            continue
    
    return ' '.join(resultado)

# Texto que quieres convertir
texto = "Hola mundo"

# Solicitar al usuario que ingrese un carácter
caracter = input("Ingresa un carácter para representar el código Morse: ")

# Convertir y mostrar el resultado
resultado = texto_a_morse(texto, caracter)
print(f"Texto original: {texto}")
print(f"Código Morse (usando '{caracter}'): {resultado}")

````
