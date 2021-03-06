---
title: Procedimiento para enviar datos mediante la clase WebRequest
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 591a1129625a4ff08c9aa37ce651bbc0320ff25d
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634276"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a>Procedimiento para enviar datos mediante la clase WebRequest
En el procedimiento siguiente se describen los pasos para enviar datos a un servidor. Este procedimiento se suele usar para publicar datos en una página web. 
  
## <a name="to-send-data-to-a-host-server"></a>Para enviar datos a un servidor host  
  
1.  Cree una instancia <xref:System.Net.WebRequest> mediante una llamada a <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con el URI de un recurso (como un script o una página ASP.NET) que acepte datos. Por ejemplo: 
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")  
    ```  
  
    > [!NOTE]
    > .NET Framework proporciona clases específicas de protocolo derivadas de las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> para identificadores URI que empiezan por *http:*, *https:*, *ftp:* y *file:*.
    Si necesita establecer o leer propiedades específicas de protocolo, debe convertir el objeto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> a un tipo de objeto específico de protocolo. Para obtener más información, vea [Programar protocolos acoplables](programming-pluggable-protocols.md). 
  
2.  Establezca los valores de propiedad que sean necesarios en el objeto `WebRequest`. Por ejemplo, para habilitar la autenticación, establezca la propiedad <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> en una instancia de la clase <xref:System.Net.NetworkCredential>:
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
3.  Especifique un método de protocolo que permita que se envíen datos con una solicitud, como el método `POST` de HTTP:  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  Establezca la propiedad <xref:System.Web.HttpRequest.ContentLength> en el número de bytes que incluya con su solicitud. Por ejemplo: 
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  Establezca la propiedad <xref:System.Web.HttpRequest.ContentType> en un valor apropiado. Por ejemplo:
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Obtenga la secuencia que contiene los datos de la solicitud llamando al método <xref:System.Net.WebRequest.GetRequestStream%2A>. Por ejemplo:
  
    ```csharp  
    Stream dataStream = request.GetRequestStream();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream()  
    ```  
  
7.  Escriba los datos en el objeto <xref:System.IO.Stream> que devuelve el método `GetRequestStream`. Por ejemplo:
  
    ```csharp  
    dataStream.Write(byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write(byteArray, 0, byteArray.Length)  
    ```  
  
8.  Cierre la secuencia de la solicitud mediante una llamada al método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Por ejemplo:
  
    ```csharp  
    dataStream.Close();  
    ```  
  
    ```vb  
    dataStream.Close()  
    ```  
  
9. Envíe la solicitud al servidor llamando a <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>. Este método devuelve un objeto que contiene la respuesta del servidor. El tipo del objeto `WebResponse` devuelto se determina mediante el esquema del URI de la solicitud. Por ejemplo:
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
10. Puede obtener acceso a las propiedades de su objeto `WebResponse` o convertirlo en una instancia específica de protocolo para leer propiedades específicas de protocolo. 

    Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta el objeto `WebResponse` en una referencia <xref:System.Net.HttpWebResponse>. En el ejemplo de código siguiente se indica cómo mostrar la propiedad <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> específica de HTTP enviada con una respuesta:
  
    ```csharp  
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);    
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, llame al método <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> del objeto `WebResponse`. Por ejemplo:
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
12. Después de leer los datos del objeto de respuesta, ciérrelo con el método <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> o cierre la secuencia de respuesta con el método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Si no cierra la respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes. Dado que el método `WebResponse.Close` llama a `Stream.Close` cuando cierra la respuesta, no es necesario llamar a `Close` en los objetos de respuesta y de secuencia, aunque hacerlo no causa ningún daño. Por ejemplo:
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Ejemplo  
  
En el ejemplo de código siguiente se muestra cómo enviar datos a un servidor web y cómo leer los datos de la respuesta:  

```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main()  
        {  
            // Create a request by using a URL that can receive a post.   
            WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  

            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes(postData);  

            // Set the ContentType property of the request.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the request.  
            request.ContentLength = byteArray.Length;  

            // Get the request stream.  
            Stream dataStream = request.GetRequestStream();  
            // Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length);  
            // Close the stream.  
            dataStream.Close();  

            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine(((HttpWebResponse)response).StatusDescription);  

            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream();  
            // Open the stream by using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  

            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  

            // Clean up the response.  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  

Namespace Examples.System.Net  

    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  

            ' Create a request by using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  

            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  

            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  

            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the stream.  
            dataStream.Close()  

            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  

            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream by using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  

            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  

            ' Clean up the response.  
            reader.Close()  
            response.Close()  

        End Sub  

    End Class  

End Namespace  
```  
  
## <a name="see-also"></a>Vea también
- [Creación de solicitudes de Internet](creating-internet-requests.md)
- [Uso de secuencias en la red](using-streams-on-the-network.md)
- [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)
- [Solicitud de datos](requesting-data.md)
- [Procedimiento para solicitar datos mediante la clase WebRequest](how-to-request-data-using-the-webrequest-class.md)
