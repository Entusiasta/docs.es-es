---
title: Transacciones de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: cb2a72bb24640d214170c52b8b3bf0a328d3f775
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714624"
---
# <a name="workflow-transactions"></a>Transacciones de flujo de trabajo

[!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona el soporte técnico para participar en las transacciones del espacio de nombres <xref:System.Transactions> usando la actividad <xref:System.Activities.Statements.TransactionScope> para abarcar una unidad de trabajo con la que se haya realizado una transacción. Aunque la clase <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> debe completarse explícitamente, la actividad <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> realiza una llamada implícita de finalización de la transacción cuando se haya completado correctamente. Las actividades que se contengan en el elemento de la propiedad <xref:System.Activities.Statements.TransactionScope.Body%2A> de la actividad <xref:System.Activities.Statements.TransactionScope> participan en la transacción. WF puede fluir las transacciones en un flujo de trabajo a través del uso de la actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Al igual que ocurre con la actividad <xref:System.Activities.Statements.TransactionScope>, cualquier actividad contenida en la propiedad <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participa en la transacción. WF garantiza que las actividades dependientes de <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> funcionan con <xref:System.Activities.Statements.TransactionScope> y <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Si las actividades proporcionadas por el sistema no afrontan todos los requisitos, las actividades personalizadas se pueden compilar usando <xref:System.Activities.RuntimeTransactionHandle> para habilitar los escenarios de flujo avanzado y del control de transacciones.  
  
En el ejemplo siguiente, se construye un flujo de trabajo que consta de un <xref:System.Activities.Statements.Sequence> actividad que contiene actividades secundarias incluida una <xref:System.Activities.Statements.TransactionScope> actividad. Las actividades <xref:System.Activities.Statements.TransactionScope.Body%2A> de <xref:System.Activities.Statements.TransactionScope> se ejecutan bajo la transacción inicializada por la actividad <xref:System.Activities.Statements.TransactionScope>.  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
Para obtener más información, consulte acerca del uso de <xref:System.ServiceModel.Activities.TransactedReceiveScope>, consulte [las transacciones que fluyen dentro y fuera de los servicios de flujo de trabajo](../wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Activities.Statements.TransactionScope>
- <xref:System.Transactions.TransactionScope>
- <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
