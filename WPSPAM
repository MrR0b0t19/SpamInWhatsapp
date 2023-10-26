from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
import time

# URL de WhatsApp Web
whatsapp_url = "https://web.whatsapp.com/"

# Lista de contactos a los que se enviara
contactos = ["Uno", "Dos", "Tres", "Cuatro", "Cinco", "Seis", "Siete", "Ocho", "Nueve", "Diez","Once", "Doce", "Trece", "Catorce", "Quince", "Dieciséis", "Diecisiete", "Dieciocho", "Diecinueve", "Veinte",
"Veintiuno", "Veintidós", "Veintitrés", "Veinticuatro", "Veinticinco", "Veintiséis", "Veintisiete", "Veintiocho", "Veintinueve", "Treinta",
"Treinta y uno", "Treinta y dos", "Treinta y tres", "Treinta y cuatro", "Treinta y cinco", "Treinta y seis", "Treinta y siete", "Treinta y ocho", "Treinta y nueve", "Cuarenta",
"Cuarenta y uno", "Cuarenta y dos", "Cuarenta y tres", "Cuarenta y cuatro", "Cuarenta y cinco", "Cuarenta y seis", "Cuarenta y siete", "Cuarenta y ocho", "Cuarenta y nueve", "Cincuenta",
"Cincuenta y uno", "Cincuenta y dos", "Cincuenta y tres", "Cincuenta y cuatro", "Cincuenta y cinco", "Cincuenta y seis", "Cincuenta y siete", "Cincuenta y ocho", "Cincuenta y nueve", "Sesenta",
"Sesenta y uno", "Sesenta y dos", "Sesenta y tres", "Sesenta y cuatro", "Sesenta y cinco", "Sesenta y seis", "Sesenta y siete", "Sesenta y ocho", "Sesenta y nueve", "Setenta",
"Setenta y uno", "Setenta y dos", "Setenta y tres", "Setenta y cuatro", "Setenta y cinco", "Setenta y seis", "Setenta y siete", "Setenta y ocho", "Setenta y nueve", "Ochenta",
"Ochenta y uno", "Ochenta y dos", "Ochenta y tres", "Ochenta y cuatro", "Ochenta y cinco", "Ochenta y seis", "Ochenta y siete", "Ochenta y ocho", "Ochenta y nueve", "Noventa",
"Noventa y uno", "Noventa y dos", "Noventa y tres", "Noventa y cuatro", "Noventa y cinco", "Noventa y seis", "Noventa y siete", "Noventa y ocho", "Noventa y nueve", "Cien"]
#mensaje de texto que deseas enviar 
mensaje = "Si a tu casa llega la encuesta, Javier May es la respuesta! Te invitamos a que elijas la mejor opción"
#Ruta de la imagen que 
#ruta_imagen = 'C:/Users/computadora/Desktop/script/fto.jpeg'
# Tiempo de espera entre mensajes (en segundos)
delay_entre_mensajes = 30  # 1 minuto
 
# Inicializar el navegador
driver = webdriver.Chrome()
driver.get(whatsapp_url)

# Esperar a que el usuario escanee el código QR manualmente 
input("Escanea el código QR de WhatsApp Web y presiona Enter cuando estés listo...")
#/html/body/div[1]/div/div/div[3]/div[2]/span/div/span/div/div/div[2]/div/div[2]/div[2]/div/div
#//*[@id="app"]/div/div/div[3]/div[2]/span/div/span/div/div/div[2]/div/div[2]/div[2]/div/div
# Función para enviar una imagen y txt a un contacto
print("en proceso")
# Espera implícita de 2 segundos
driver.implicitly_wait(2)
def enviar_imagen_a_contacto(contacto, mensaje): #, ruta_imagen
    try:
        # campo de búsqueda
        search_box = driver.find_element(By.XPATH, '/html/body/div[1]/div/div/div[4]/div/div[1]/div/div[2]/div[2]/div/div[1]/p')
        search_box.clear()
        search_box.send_keys(contacto)
        search_box.send_keys(Keys.RETURN)

        # Esperar un momento para que aparezca la conversación
        time.sleep(3)

        # Adjuntar la imagen
        #attachment_button = driver.find_element(By.XPATH, '/html/body/div[1]/div/div/div[5]/div/footer/div[1]/div/span[2]/div/div[1]/div/div/div/div/span')
        #attachment_button.click()
        #image_option = driver.find_element(By.XPATH, '/html/body/div[1]/div/div/div[5]/div/footer/div[1]/div/span[2]/div/div[1]/div/div/span/div/ul/div/div[2]/li')
        #image_option.send_keys(ruta_imagen)
        #time.sleep(2)

        # Enviar el mensaje
        input_box = driver.find_element(By.XPATH, '/html/body/div[1]/div/div/div[5]/div/footer/div[1]/div/span[2]/div/div[2]/div[1]/div/div[1]/p')
        input_box.send_keys(mensaje)#, ruta_imagen)
        input_box.send_keys(Keys.RETURN)
        time.sleep(.5)


        #envio de la imagen tomando mecanismo de portapapeles
        attachment_button = driver.find_element(By.XPATH, '/html/body/div[1]/div/div/div[5]/div/footer/div[1]/div/span[2]/div/div[2]/div[1]/div/div[1]/p')
        attachment_button.send_keys(Keys.CONTROL, 'v')
        attachment_button = driver.find_element(By.XPATH, '//*[@id="app"]/div/div/div[3]/div[2]/span/div/span/div/div/div[2]/div/div[2]/div[2]/div/div')#.click()
        #time.sleep(.1)
        attachment_button.click()
      


    except Exception as e:
        print(f"No se pudo enviar la verga esa a {contacto}: {str(e)}")

# Loop para enviar imágenes a cada contacto en la lista
for contacto in contactos:
    enviar_imagen_a_contacto(contacto, mensaje) #, ruta_imagen#)
    time.sleep(delay_entre_mensajes)

# Cerrar el navegador cuando hayas terminado

# Mensaje de éxito
print("SE HA COMPLETADO EL SPAM FELICIDADES SOS UN HACKER ATTE: Fan_tasma xD")
driver.quit()
