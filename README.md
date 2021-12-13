# Proyecto-1
#Primer parte del proyecto Emtech 
if __name__ == "__main__":
    # Nuestro usuario y nuestra contraseña prueba es:
    USUARIO = 'Pro1'
    CONTRASENA = 'Emtech'

    #  La cantidad de intentos permitidos será:
    INTENTOS = 3

    # Vamos a controlar la cantidad de repeticiones
    # dentro del ciclo usando nuestra variable 'intentos',
    # nuestras condiciones de escape son 2:
    #  * que se termine la cantidad de intentos posibles
    #  * que acceda correctamente
    while True:
        # Antes de dejarle intentar, veamos si tiene intentos
        if INTENTOS == 0:
            # En caso de que no tenga intentos, terminaremos
            # con el programa
            exit()
        username = input('Hola, \n Para iniciar sesión ingrese su nombre de usuario:\n > ')
        password = input('Ingrese su contraseña:\n > ')
        # revisemos si son correctos
        if username == USUARIO:
        # En este punto, la persona ingreso correctamente
        # el usuario, comprobemos la contraseña ahora.
            if password == CONTRASENA:
                # Llegado a este punto, el ciclo puede terminar
                # la persona ingreso correctamente usuario y
                # contrasena
                break
        else:
            # En caso de que el usuario no sea correcto,
            # no hace falta ya comprobar la contraseña.
            # Le restamos un intento directamente y le hacemos
            # saber sobre su error, y la cantidad de intentos
            # restantes.
            INTENTOS = INTENTOS - 1
            
            print(f'\n!! Usuario/Contraseña incorrecto(s), {INTENTOS} restantes !!\n')

    print(f"\n\n\n ¡Bienvenido! {USUARIO},\n ¡Ingreso exitoso!")

    print("¿Qué le gustaría hacer primero?")


    
espaciosenblanco = '\n' * 7

menu_principal = """
· · · · · Menú Principal · · · · ·

A continuación usted podrá seleccionar en la 
parte de abajo del menú que lista desea ver primero:

[1] Productos vendidos y rezagados

[2] Productos por reseña en el servicio

[3] Resultados de ventas e ingresos


"""
print (menu_principal)

opcion = input ('Digita una opción: \n > ')


if opcion == '1':

  menu_1 = """" 
      ······  1. PRODUCTOS VENDIDOS Y REZAGADOS ······ 

       [1.1] Top 5 mayores ventas
       [1.2] Top 10 mayores busquedas
       [1.3] Categorías (menos vendidas & menos buscadas)


  """ 
  print (menu_1)

  while True:
    opcion = input ('Digita una opción: \n > ' )
    if opcion =='1.1':
      print (('···' * 20) + ('\n' *2))
      print (' \n El top 5 de los productos con mayores VENTAS es: ')
    
  
    elif opcion == '1.2':
      print (('···' * 20) + ('\n' *2))
      print (' \n El top 10 de los productos con mayores BÚSQUEDAS es: \n ')
      

    elif opcion == '1.3':
      menu_categoria = """ 

       1.3 CATEGORÍAS
           
           [1.3.1] Top 5 menos vendidas
           [1.3.2] Top 5 menos buscadas

      """
      print (('···' * 20) + ('\n' ) )
      print (menu_categoria)
      print (' \n ')
      print (('···' * 20) + ('\n' ) )
      while True:
        opcion = input ('Digita una opción: \n > ' )
        if opcion == '1.3.1':
         print (('···' * 20) + ('\n' *2 ) )
         print ('\n Los 5 productos por categoría MENOS  VENDIDOS son:\n')
         
    
        elif opcion =='1.3.2': 
          print (('···' * 20) + ('\n' *2 ) )
          print ('Los 5 productos por categoría MENOS BUSCADOS son: \n ')
          
        else:
         pass 
         # opcion = input ('Digita una opción: \n > ' )
    else:
      pass
      #return (opcion)
      break
    
elif opcion == '2':

  menu_2 = """
     ······  2. PRODUCTOS POR RESEÑA EN EL SERVICIO ······ 
      
      [2.1] Top 5 P. con mejores reseñas
      [2.2] Top 5 P. con peores reseñas
  """
  print (menu_2)

  while True:
    opcion = input ('Digita una opción: \n > ' )
    if opcion =='2.1':
      print ('···' * 20)
      print (' \n El top 5 de los productos con MEJORES RESEÑAS es: \n ')
      
    elif opcion == '2.2':
      print ('···' * 20)
      print (' \n El top 5 de los productos con PEORES RESEÑAS es: \n ')
      

    else:
      pass
      #return opcion = input ('Digita una opción: \n > ' )

# Resultados de ventas e ingresos

elif opcion =='3':

  menu_3 = """

 ······  3.  RESULTADOS DE VENTAS E INGRESOS ······

 [3.1] NÚMERO DE VENTAS

 [3.2] TOTAL DE INGRESOS
  
  """
print (menu_3)

while True:
    opcion = input ('Digita una opcion: \n >')
    if opcion =='3.1':
      print ('···' * 20)
      menu_numero_ventas = """" 

      ····· 3.1 NÚMERO DE VENTAS ······

     [3.1.1] Promedio promedio_mensual
     [3.1.2] Total anual
     [3.1.3] Meses con más ventas del año """

      print (menu_numero_ventas)
      
    elif opcion == '3.2':
      print ('···' * 20)
      menu_total_ingresos =""" 

      ······ 3.2 TOTAL DE INGRESOS ······
      [3.2.1] Promedio mensual
      [3.2.2] Total anual
      [3.2.3] Meses con más ventas del año
      
      """
      print (menu_total_ingresos)
      # (' \n El top 5 de los productos con PEORES RESEÑAS es: \n')

from lifestore_file import lifestore_products, lifestore_sales, lifestore_searches
"""
This is the LifeStore_SalesList data:

lifestore_products = [ 0 id_product, 1 name, 2 price, 3 category, 4 stock]

lifestore_searches = [0 id_search, 1 id product]
lifestore_sales = [0 id_sale, 1 id_product, 2 score (from 1 to 5), 3 date, 4 refund (1 for true or 0 to false)]

"""

#for producto in lifestore_sales:
  #id = producto [1]
  #nombre = producto [1][:10]
  #precio = producto[2] 
  #categoria = producto [3]
  #print (f'La categoría {categoria} tiene )

  #print (f'El precio de {nombre} es de {precio}')

#Suma de todos los productos de la categoría 'discos duros'
 #categorias_discos_duros = []
#for producto in lifestore_products:
 # cat_prod = producto [3]
 # if cat_prod == categoria_buscada:
   # categoria_discos_duros.append (producto)

#for prod in categoria_discos_duros:
 # print (prod)
  


  # Ventas Validas
ventas = []
# lifestore_sales = [id_sale, id_product, score (from 1 to 5), date, refund (1 for true or 0 to false)]
for sale in lifestore_sales:
    # refund = sale[-1]
    refund = sale[4]
    # tipo numero: 1
    # tipo string: '1'
    if refund == 1:
        continue
        # break
        # pass
    else:
        ventas.append(sale)

# print(ventas)
# for venta in ventas:
    # print(venta)
# Aqui ventas ya tiene unicamente las ventas validas (no incluye reembolsos)

# completen con el resto de meses
meses = [
    '/01/', '/02/', '/03/', '/04/', '/05/', '/06/',
    '/07/', '/08/', '/09/', '/10/', '/11/', '/12/'
    ]
    
ventas_por_mes = []
for mes in meses:
    lista_vacia = []
    ventas_por_mes.append(lista_vacia)

for venta in ventas:
    # Datos de la venta
    id_venta = venta[0]
    fecha = venta[3]

    # Clasificar en mes
    # Comienzo en el mes 0 ('/01/')
    contador_de_mes = 0

    for mes in meses:
        if mes in fecha:
            ventas_por_mes[contador_de_mes].append(id_venta)
            continue
        contador_de_mes = contador_de_mes + 1 



contador_de_mes = 0
for venta_mensual in ventas_por_mes:
    print(f'En el mes de {meses[contador_de_mes]} hubo {len(venta_mensual)} ventas!')
    contador_de_mes = contador_de_mes + 1

#Vamos a encontrar CUANTO (en dinero) se vendió cada mes.
#print (ventas_por_mes[0])

"""
#· Primero obtengamos la lista de los IDs de venta de un mes
   ventas_de_enero = ventas_por_mes[0]
#· Luego, obengamos el primer ID de venta en esta lista.
   primer_venta_de_enero = ventas_de_enero[0]
   print(primer_venta_de_enero) # Mostremos el ID
#· Usemos el ID - 1, como indice para acceder a toda la informacion
#· en nuestra lista de ventas
   print(lifestore_sales[primer_venta_de_enero - 1])
   indice = primer_venta_de_enero - 1
   info_de_venta = ventas[indice]
#· De toda la informacion de la venta, obtengamos el ID del producto
#· que se vendio en esa transaccion
   id_prod = info_de_venta[1]
#· Utilicemos este ID de producto, restandole 1
#· para encontrar toda la informacion del producto
#· en la lista de productos
   producto = lifestore_products[id_prod - 1]
   print(producto)
#· Teniendo toda la info del producto, obtengamos
   el precio
   precio_del_prod = producto[2]
   print(precio_del_prod)
"""
ganancias_mensuales = []
for venta_mensual in ventas_por_mes:
    ganancia_del_mes = 0
    for id_venta in venta_mensual:
        indice_de_venta = id_venta - 1
        
        info_de_venta = lifestore_sales[indice_de_venta]

        id_prod = info_de_venta[1]
        indice_de_prod = id_prod - 1
        info_del_prod = lifestore_products[indice_de_prod]
        precio_de_prod = info_del_prod[2]
        ganancia_del_mes = ganancia_del_mes + precio_de_prod
    ganancias_mensuales.append(ganancia_del_mes)

ganancia_mes = []
for mes, ganancia in enumerate(ganancias_mensuales):
    sublista = [ganancia, mes]
    ganancia_mes.append(sublista)
  

# for lista in lista_prev:
#     print(lista)

# lista_prev.sort(reverse=True)
# print('Ahora en orden: ')
# for lista in lista_prev:
#     print(lista)


cantidad_ventas_mensuales = []
for mes, venta_mensual in enumerate (ventas_por_mes):
    cant_ventas_mensuales = len(venta_mensual)
    sublista = [cant_ventas_mensuales, mes]
    cantidad_ventas_mensuales.append(sublista)

for cantidad in cantidad_ventas_mensuales:
     print(cantidad)

cantidad_ventas_mensuales.sort(reverse=True)

for par in cantidad_ventas_mensuales:
  print(par)


for ganancia_mes in ganancias_mensuales:
  print (ganancia_mes)

ganancias_mensuales.sort (reverse = True)

for par in ganancias_mensuales:
  print (par)
 
prod_reviews = []
for prod in lifestore_products:
    id_prod = prod[0]
    sublista = [id_prod, 0 , 0]
    prod_reviews.append(sublista)
# en lugar de lifestroe_sales poner ventas[0]
for venta in ventas [0]:
    id_prod = venta[1]
    review = venta[2]
    
    indice = id_prod - 1
    prod_reviews[indice][1] += review
    prod_reviews[indice][2] += 1
    
for indice, lista in enumerate(prod_reviews):
   suma = lista[1]
   cant = lista[2]
   if cant > 0:
       calf_prom = suma / cant
       prod_reviews[indice][1] = calf_prom

""""
Aqui prod_reviews ya tiene la forma
[id_prod, review promedio, cant. de ventas]
"""

# # Para obtener los mejor calificados:
# mejores_calificados = []
# for lista in prod_reviews:
#     sublista = [lista[1], lista[0]]
#     mejores_calificados.append(sublista)


# mejores_calificados.sort(reverse=True)
# for rev in mejores_calificados[:5]:
#     print(rev)

    
# Para obtener los mas vendidos:
mejores_vendidos= []
for lista in prod_reviews:
    sublista = [lista[2], lista[0], lista[1]]
    mejores_vendidos.append(sublista)


mejores_vendidos.sort(reverse=True)
for rev in mejores_vendidos[:5]:
    print(rev)  

# for venta in lifestore_sales:
#     id_prod = venta[1] 

# Para obtener los mas vendidos:
#mejores_vendidos= []
#for lista in prod_reviews:
 #   sublista = [lista[2], lista[0], lista[1]]
  #  mejores_vendidos.append(sublista)

#peores_vendidos.sort(reverse=True)
#for rev in peores_vendidos[:1]:
 #   print(rev)   

