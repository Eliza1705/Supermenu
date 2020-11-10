main = do
      pregunta True
--SUPERMENU
pregunta seguir = do
    if seguir
        then do
        putStrLn "************** SUPER MENU***************"
        putStrLn "1.- calculadora"
        putStrLn "2.-Presentar numeros"
        putStrLn "3.-Serie Fibonacci"
        putStrLn "4.-Palindromo"
        putStrLn "5.-Desaparece numeros"
        putStrLn "6.-Factorial"
        putStrLn "7.-Salir"
        opcion <- getLine

        case opcion of
            "1" -> menu
            "2" -> numeros
            "3" -> fibonacci
            "4" -> palindromo
            "5" -> desaparece
            "6" -> datos
            "7" -> salir
            _ -> print("Opcion invalida")
            --"3" -> do
                --putStrLn("Dame un numero")
                --n <- getLine
                --let nInt = read n::Int
               -- factorial nInt
                
            --"4" ->do
               -- putStrLn ("Dame un palindromo")
                --p <- getLine
               -- let pInt = read p:: Int
               -- palindromo p
            --"5" -> desaparece

        
          
    else
        putStrLn "adios"
--CASO CALCULADORA
menu = do
    putStrLn "****************MENU CALCULADORA****************"
    putStrLn "1.- Suma"
    putStrLn "2.- Resta"
    putStrLn "3.- Multiplicacion"
    putStrLn "4.-Division"
    putStrLn("¿Cual caso quieres? ") 
    n <- getLine
    casos n

casos  n= do
    case n of 
        "1" ->suma
        "2" ->resta
        "3" ->multiplicacion
        "4" ->division
        "5" ->pregunta False
        _ -> print ("Opcion invalida")

suma = do
    putStrLn("numero 1: ")
    a <- readLn    
    putStrLn("numero 2: ")
    b <- readLn
    print ("El resultado es "++ show(a+b))
    pregunta True

resta = do
    putStrLn("numero 1: ")
    a <- readLn    
    putStrLn("numero 2: ")
    b <- readLn
    print ("El resultado es "++ show(a-b))
    pregunta True

multiplicacion = do
    putStrLn("numero 1: ")
    a <- readLn    
    putStrLn("numero 2: ")
    b <- readLn
    print ("El resultado es "++ show(a*b))
    pregunta True

division = do
    putStrLn("numero 1: ")
    a <- readLn    
    putStrLn("numero 2: ")
    b <- readLn
    print ("El resultado es "++ show(a/b))
    pregunta True
     
--CASO PRESENTACION DEL 1 AL 10
numeros = do
    presentacion 1

presentacion n = do
    if n<=10
        then do
            print n
            presentacion (n+1)
      else do
            pregunta True

--CASO FACTORIAl
datos = do
    putStrLn("Dame un numero")
    numero <-getLine
    print ("factorial es:"++ show (factorial(read numero)))
    pregunta True
factorial n= if n==0 then 1
            else n*factorial(n-1)
    
                


--factorial n = do  
    --putStrLn ("Dame un numerito")
    --n <- getLine
    --let nInt = read n::Int
        --if n==0
            --then 1
        --else n* factorial (n-1)

--factorial :: Integer -> Integer
--factorial nInt = if nInt==0 then 1
            --else nInt* factorial (nInt-1)

--factorial = do
   -- putStrLn("Ingrese un numero")
   -- n <- getLine
   -- n:: Integer -> Integer
   --if n==0 then 1
--else n*( n(n-1)

--CASO PALINDROMO
palindromo = do
    putStrLn ("Palabra para revisar")
    c <- getLine
    let res = c== reverse c

    if res==True
        then do
            putStrLn ("Yeiiii, si es palindromo")
            pregunta True
    else do
        putStrLn ("oh oh! ese no es un palindromo")
        pregunta True


--CASO DESAPARECE NUMEROS

desaparece = do
    arreglo [0,1,2,3,4,5,6,7,8,9,10]
    pregunta True
arreglo i= 
    if null i
        then 
        print ("Ya")
    else do
        print (i)
        arreglo(init i)
--CASO FIBONACCI

fibonacci = do
    putStrLn "Ingresa la posicion"
    n <- getLine
    let nInt = read n::Int
    serie nInt

serie nInt= do
    let arreglo = ["0", "11" , "1", "34" ,"3","5","66", "7","23","10"]

    if(nInt<= 9)
        then do
            print (arreglo !! nInt)
            --serie (nInt+1)
            pregunta True
    else do
        --main
        pregunta True

--SALIR
salir = do
    pregunta False

