#PruebaDiaggnostica
def main():
    entrada = input("Ingrese valor(es):_")
    datos = entrada.split()
    numeros = []
    for i in range(len(datos)):
        numeros.append(int(datos[i]))
    for num in numeros:
        print("Para el valor ingresado:", num)
        pos_neg_nul(num)
        par_impar(num)
        fibonacci(num)
        primo(num)
        if len(numeros) > 1:
            sum_interva(num, numeros[-1])
        imp_par(num)
        print("------------------------------------------------")
    cod=codigo_est()
    fech=fech_nacimient()
    print("Para el código ingresado:",cod)
    pos_neg_nul(cod)
    par_impar(cod)
    fibonacci(cod)
    primo(cod)
    imp_par(cod)
    mes_resulta(fech)
    pos_letr(fech)  
#PUNTO 1
def pos_neg_nul (n):
    if n>0:
        print("Su número es Positivo.")
    if n<0:
        print("Su número es negativo.")
    if n== 0:
        print("Su número es 0.")
#PUNTO 2
def par_impar(n):
    if n%2==0:
        print("Su número es par.")
    else:
        print("Su número es impar.")
#PUNTO 3
def fibonacci(n):
    a = 0
    b = 1
    while a < n:
        c = a + b
        a = b
        b = c
    if a == n:
        print("El número pertenece a Fibonacci")
    else:
        print("El número NO pertenece a Fibonacci")
#PUNTO 4
def primo (n):
    if n<2:
        print("No es un número primo.")
        return
    if n%1==0 and n%n==0:
        for i in range(2,n):
            if n%i==0:
                print("No es un número primo.")
                return
    print("Es un número primo.")
#PUNTO 5
def sum_interva(n1,n2):
    val=0
    for i in range (n1+1,n2):
        val=val+i
    print("La suma desde",n1,"hasta",n2,"es igual a",val)
#PUNTO 6
def imp_par(n):
    val=0
    if n%2==0:
        val=n*n*n
        print ("El número elevado al cubo es",val)
        return 
    else:
        val=n*n
        print ("El número elevado al cuadrado es",val)
        return    
#PUNTO 7
def codigo_est():
    cod=int(input("Ingrese código de estudiante:_"))
    return (cod)
#PUNTO 8
def fech_nacimient():
    fech=input("Ingrese la fecha de nacimiento, ejemplo: 1enero2000100032300:_")
    return(fech)
#PUNTO 9
def mes_resulta(fech):
    meses = ["enero", "febrero", "marzo", "abril", "mayo", "junio",
         "julio", "agosto", "septiembre", "octubre", "noviembre", "diciembre"]
    for i in range(len(meses)):
        if meses[i] in fech:
            mes = meses[i]
    cntvoc = 0
    cntcons = 0
    for i in range(len(mes)):
        if mes[i] == "a" or mes[i] == "A" or mes[i] == "e" or mes[i] == "E" or mes[i] == "i" or mes[i] == "I" or mes[i] == "o" or mes[i] == "O" or mes[i] == "u" or mes[i] == "U":
            cntvoc = cntvoc + 1
        else:
            cntcons = cntcons + 1
    print("Del mes resultante hay", cntvoc, "vocales y", cntcons, "consonantes.")
#PUNTO 10
def pos_letr(fech):
    poslet=0
    abe=["a","b","c","d","e","f","g","h","i","j","k","l","m","n","ñ","o","p","q","r","s","t","u","v","w","x","y","z"]
    for i in range(len(fech)):
        letra = fech[i].lower() 
        if letra in abe:        
            poslet = abe.index(letra) + 1  
            print(letra,"Número de letra", poslet)
main()