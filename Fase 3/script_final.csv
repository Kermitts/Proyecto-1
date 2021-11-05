#Hemos usado la plantilla del script y lo hemos modificado
#Script:


#./menu.ps1 param1 param2
#o 
#./menu.ps1 -Param1 parametro1 -Param2 parametro2
#Los parámetros son opcionales, si la llamada es:./menu.ps1 --> los valores de $Param1 y $Param2, será la cadena de texto vacía.
Param(
  [string]$Param1,
  [string]$Param2
)
Write-Host "Los parámetros son:"$Param1 " " $Param2
pause

#Función 1. Promocionar a CD
function promocionarCD
{
Write-Host "a"
}


function mostrarMenu 
{ 
     param ( 
           [string]$Titulo = 'Selección de opciones' 
     ) 
     Clear-Host 
     Write-Host "================ $Titulo================" 
      
     
     Write-Host "1) Crear usuario" 
     Write-Host "2) Segunda Opción" 
     Write-Host "3) Crear Unidad Organizativa"
     Write-Host "4) Deshabilitar cuenta de usuario" 
     Write-Host "S) Presiona 'S' para salir" 
}
#Bucle principal del Script. El bucle se ejecuta de manera infinita hasta que se cumple
#la condición until ($input -eq 's'), es decir, hasta que se pulse la tecla s.
do 
{ 
     #Llamamos a la función mostrarMenu, para dibujar el menú de opciones por pantalla
     mostrarMenu 
     #Recogemos en la varaible input, el valor que el usuario escribe por teclado (opción del menú)
     $input = Read-Host "Elegir una Opción" 
     #https://ss64.com/ps/switch.html
     switch ($input) 
     { 
           '1' { 
                New-ADUser -Name "George" -Path "OU=Administracion Parcial 1, DC=edu-gva, DC=es" -SamAccountName "George" -UserPrincipalName "george@edu-gva.es" -AccountPassword (ConvertTo-secureString "Chubbyemu01" -AsPlainText -Force) -GivenName "George" -Surname "george" -ChangePAsswordAtLogon $true -Enabled $true
                'Crear usuario' 
                pause
           } '2' { 
                Remove-ADUser -Identity "CN=Sebastian, OU=Administracion Parcial 1, DC=edu-gva, DC=es"  
                'Eliminar usuario' 
                pause
           } '3' { 
                New-ADOrganizationalUnit -Name "Administracion Parcial 1"
                'Crear Unidad Organizativa' 
                pause
           } '4' { 
                Disable-ADAccount -Identity "CN=Sebastian, OU=Administracion Parcial 1, DC=edu-gva, DC=es"
                'Deshabilitar cuenta de usuario' 
                pause
           } 's' {
                'Saliendo del script...'
                return 
           } 
           #Si no se selecciona una de las opciones del menú, es decir, se pulsa algun carácter
           #que no sea 1, 2, 3 o s, sacamos por pantalla un aviso e indicamos lo que hay que realizar.
           default { 
              'Por favor, Pulse una de las opciones disponibles [1-3] o s para salir'
           }
     } 
     pause 
} 
until ($input -eq 's')
