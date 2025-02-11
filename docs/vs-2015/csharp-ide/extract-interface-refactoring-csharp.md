---
title: Extrahování rozhraní refaktoring (C#) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.csharp.refactoring.extractinterface
dev_langs:
- CSharp
helpviewer_keywords:
- refactoring [C#], Extract Interface
- Extract Interface refactoring operation [C#]
ms.assetid: 7d0aa225-3b33-4331-9652-5a67cac6f3d0
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: deb2e446ff051b52e9c34d28abfa99436c064ad6
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65680910"
---
# <a name="extract-interface-refactoring-c"></a>Refaktoring pro extrahování rozhraní (C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Extrahování rozhraní se operaci refaktoringu, která poskytuje snadný způsob, jak vytvořit nové rozhraní s členy, které pocházejí z existující třídy, struktury nebo rozhraní.  
  
 Několik klientů, použijete stejnou podmnožinu členů ze třídy, struktury nebo rozhraní, nebo pokud více třídy, struktury nebo rozhraní mají podmnožinu členů společné, může být užitečné začleněné podmnožinu členů v rozhraní. Další informace o použití rozhraní najdete v tématu [rozhraní](https://msdn.microsoft.com/library/2feda177-ce11-432d-81b4-d50f5f35fd37).  
  
 Extrahování rozhraní generuje rozhraní v novém souboru a umístí kurzor na začátku nového souboru. Můžete určit, které členy mají extrahovat do nové rozhraní, název nového rozhraní a název generovaného souboru pomocí **extrahování rozhraní** dialogové okno.  
  
### <a name="to-use-extract-interface"></a>Chcete-li použít extrahování rozhraní  
  
1. Vytvořte konzolovou aplikaci s názvem `ExtractInterface`a potom nahraďte `Program` následujícím kódem  
  
    ```csharp  
    // Invoke Extract Interface on ProtoA.  
    // Note:  the extracted interface will be created in a new file.  
    class ProtoA  
    {  
        public void MethodB(string s) { }  
    }  
    ```  
  
2. S kurzorem umístěným v `MethodB`a klikněte na tlačítko **extrahování rozhraní** na **Refaktorovat** nabídky.  
  
     **Extrahování rozhraní** zobrazí se dialogové okno.  
  
     Můžete také zadat klávesové zkratky CTRL + R, můžu pro zobrazení **extrahování rozhraní** dialogové okno.  
  
     Můžete také kliknout pravým tlačítkem myši, přejděte na **Refaktorovat**a potom klikněte na tlačítko **extrahování rozhraní** zobrazíte **extrahování rozhraní** dialogové okno.  
  
3. Klikněte na tlačítko **Vybrat vše**.  
  
4. Klikněte na **OK**.  
  
     Zobrazí se nový soubor, IProtoA.cs a následující kód:  
  
    ```csharp  
    using System;  
    namespace TopThreeRefactorings  
    {  
        interface IProtoA  
        {  
            void MethodB(string s);  
        }  
    }  
    ```  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce je přístupná pouze, když se kurzor do třídy, struktury nebo rozhraní, které obsahuje členy, které chcete extrahovat. Když je ukazatel myši na této pozici, vyvolejte operace refaktoringu extrahovat rozhraní.  
  
 Při vyvolání extrahování rozhraní, třídy nebo struktury seznamu základních tříd a rozhraní je změněno na zahrnovaly nový název rozhraní. Při vyvolání extrahování rozhraní na rozhraní seznamu základních tříd a rozhraní se nezmění.  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](../csharp-ide/refactoring-csharp.md)