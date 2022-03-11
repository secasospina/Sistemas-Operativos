#Integrantes
#Luis Fernando Bastidas        1004546496
#Sebastian Castaño Ospina      1087562075

def buscar(pr,n):
    #ordenar
    te=0                                                #tiempo de espera
    ts=0                                                #tiempo de sistema
    te1=0                                               #auxiliar de tiempo de espera
    pr1=[] #grupo rafaga
    pr2=[] #grupo llegada

    for i in range(n):              #separar la rafaja de cpu y tiempo de entrada en listas diferentes 
        pr1.append(pr[i][1])
        pr2.append(pr[i][2])
    
    pr1.remove(pr1[0])              #Eliminamos el primer valor de cada lista, puesto que este no se utiliza para este calculo
    pr2.remove(pr2[0])              
    
    for numpasada in range(len(pr1)-1,0,-1):  #Ordenamos la lista de rafaja teniendo encuenta tambien que esta conectada con la lista de tiempo de entrada
        for i in range(numpasada):

            if pr1[i] == pr1[i+1]:   #en el caso de encontrar rafajas con igua valor tiene encuanta el tiempo de llegada
                if pr2[i]>pr2[i+1]:
                    temp3 = pr2[i]
                    pr2[i] = pr2[i+1]
                    pr2[i+1] =temp3

            if pr1[i]>pr1[i+1]:
                temp = pr1[i]
                pr1[i] = pr1[i+1]
                pr1[i+1] = temp

                temp2 = pr2[i]
                pr2[i] = pr2[i+1]
                pr2[i+1] = temp2
    
    pr1.insert(0,pr[0][1])                   #Una vez ordenadas las listas, añadimos nuevamente el primer valor que habiamos eliminado anteriormente
    pr2.insert(0,pr[0][2])
    
    for i in range(n):               
        te=te+pr1[i]              
        if i <= (n-2):   #quitamos la ultima posicion porque para encontrar "te" no es necesario conocer su valor 
            te1+=(te-pr2[i+1])
        ts+=(te-pr2[i])     #calculamos el tiempo del sistema
    
    print("El valor de espera es igual a: ",te1/n)
    print("El tiempo del sistema es igual a: ",ts/n)
        


#Ingreso de los valores de proceso
#proceso = [[1, 8, 0],[2,6,2],[3,4,4],[4,2,6]]   #Sin Valores de rafaja iguales
proceso = [[1, 8, 0],[2,4,4],[3,4,2],[4,2,6]]    #Con Valores de rafaja iguales
n=4 #Numero de procesos

buscar(proceso,n)
