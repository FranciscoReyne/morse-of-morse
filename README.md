# Reyne´s Morse
Código python que convierte texto a código Morse utilizando una letra como base.

Text to morse code using my own style.
 
````
def texto_a_morse(texto, caracter):
    # Diccionario de código Morse utilizando "." para punto y "-" para raya
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
    palabras = texto.upper().split()
    
    for palabra in palabras:
        morse_palabra = []
        for letra in palabra:
            if letra in morse_dict:
                # Convertir el patrón morse a la representación con el carácter
                codigo = ""
                for simbolo in morse_dict[letra]:
                    if simbolo == '.':
                        codigo += caracter + " "  # Un carácter para punto
                    elif simbolo == '-':
                        codigo += caracter*2 + " "  # Dos caracteres para raya
                
                # Quitar el espacio extra al final de cada letra
                codigo = codigo.strip()
                morse_palabra.append(codigo)
        
        # Unir las letras de la palabra con tres espacios
        resultado.append("   ".join(morse_palabra))
    
    # Unir las palabras con slash rodeado de espacios
    return " / ".join(resultado)

# Texto que quieres convertir
texto = "Hola mundo"

# Solicitar al usuario que ingrese un carácter
caracter = input("Ingresa un carácter para representar el código Morse: ")

# Convertir y mostrar el resultado
resultado = texto_a_morse(texto, caracter)
print(f"Texto original: {texto}")
print(f"Código Morse (usando '{caracter}'): {resultado}")
````
