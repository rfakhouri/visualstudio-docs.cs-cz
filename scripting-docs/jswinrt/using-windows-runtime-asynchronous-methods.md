---
title: Použití asynchronních metod Windows Runtime | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 215a04a2f3f875743a7fbf910a3a565cf34fb558
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792012"
---
# <a name="using-windows-runtime-asynchronous-methods"></a>Použití asynchronních metod Windows Runtime
Mnoho prostředí Windows Runtime metody, hlavně metody, které může trvat dlouhou dobu pro dokončení, jsou asynchronní. Tyto metody vrací obecně asynchronní akce nebo operace (například `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, nebo `Windows.Foundation.IAsyncOperationWithProgress`). Tyto metody jsou reprezentována v jazyce JavaScript pomocí [CommonJS/lišící/A](http://go.microsoft.com/fwlink/p/?LinkId=244434) vzor. To znamená, že budou vracet Promise objekt, který má [pak](https://msdn.microsoft.com/en-us/library/windows/apps/br229728.aspx) funkce, pro které je nutné zadat `completed` funkce, která zpracovává výsledek, pokud je operace úspěšná. Pokud nechcete, aby k poskytování obslužná rutina, měli byste použít [provádí](https://msdn.microsoft.com/en-us/library/windows/apps/hh701079.aspx) funkce místo `then` funkce.  
  
> [!IMPORTANT]
>  Prostředí Windows Runtime funkcí nejsou k dispozici pro aplikace, které běží v aplikaci Internet Explorer.  
  
## <a name="examples-of-asynchronous-methods"></a>Příklady asynchronních metod  
 V následujícím příkladu `then` funkce přebírá parametr, který představuje dokončené hodnotu `createResourceAsync` metoda.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
    .then(function(newItem) {   
        console.log("New item is: " + newItem.id);  
            });  
```  
  
 V takovém případě pokud `createResourceAsync` metoda selže, vrátí příslib v chybovém stavu, ale není vyvolána výjimka. Chybu můžete řešit pomocí `then` funkce následujícím způsobem.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
    .then(function(newItem) {   
              console.log("New item is: " + newItem.id);  
          }  
          function(err) {  
              console.log("Got error: " + err.message);  
          });  
```  
  
 Pokud nechcete, aby ke zpracování chyby explicitně, ale má být vyvolána výjimka, můžete použít `done` funkce místo.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
      .done(function(newItem) {   
               console.log("New item is: " + newItem.id);  
            });  
```  
  
 Můžete také zobrazit pokroku při dokončení pomocí třetí funkce.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
      .then(function(newItem) {   
               console.log("New item is: " + newItem.id);  
            },  
    // Error.  
            function(error) {   
               alert("Failed to create a resource.");  
            },  
    // Progress.  
            function(progress, resultSoFar) {   
               setProgressBar(progress);  
            });  
```  
  
 Další informace o asynchronní programování najdete v tématu [asynchronní programování v jazyce JavaScript](https://msdn.microsoft.com/en-us/library/windows/apps/hh700330.aspx).  
  
## <a name="see-also"></a>Viz také  
 [Pomocí prostředí Windows Runtime v jazyce JavaScript](../jswinrt/using-the-windows-runtime-in-javascript.md)