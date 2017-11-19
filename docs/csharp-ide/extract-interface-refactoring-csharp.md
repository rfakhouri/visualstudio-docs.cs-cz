---
redirect_url: /visualstudio/csharp-ide/refactoring/extract-interface
title: "Extrahování rozhraní refaktoring (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Extract Interface
- Extract Interface refactoring operation [C#]
ms.assetid: 7d0aa225-3b33-4331-9652-5a67cac6f3d0
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4ed81f6f0fbcc2e72fd57d7706b051dcdf7bea75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="extract-interface-refactoring-c"></a>Refaktoring pro extrahování rozhraní (C#)
Operace refaktoringu, která poskytuje snadný způsob, jak vytvořit nové rozhraní se členy, které pocházejí z existující třída, struktura nebo rozhraní je extrakce rozhraní.  
  
 Když v několika klientech použít stejné podmnožinu členů z třída, struktura nebo rozhraní, nebo když více tříd, struktur nebo rozhraní mají podmnožinu členů společné, může být užitečné obsahují, do něj podmnožinu členů v rozhraní. Další informace o používání rozhraní najdete v tématu [rozhraní](/dotnet/csharp/programming-guide/interfaces/index).  
  
 Extrahování rozhraní generuje rozhraní do nového souboru a umístí kurzor na začátek nový soubor. Můžete určit, kteří členové extrahovat do nové rozhraní, název nové rozhraní a název vygenerovaný soubor pomocí **extrahování rozhraní** dialogové okno.  
  
### <a name="to-use-extract-interface"></a>Extrahování rozhraní použít  
  
1.  Vytvořte konzolovou aplikaci s názvem `ExtractInterface`a potom můžete nahradit `Program` následujícím kódem  
  
    ```csharp  
    // Invoke Extract Interface on ProtoA.  
    // Note:  the extracted interface will be created in a new file.  
    class ProtoA  
    {  
        public void MethodB(string s) { }  
    }  
    ```  
  
2.  Umístěte kurzor v `MethodB`a klikněte na tlačítko **extrahování rozhraní** na **Refaktorovat** nabídky.  
  
     **Extrahování rozhraní** zobrazí se dialogové okno.  
  
     Můžete také zadat klávesovou zkratku CTRL + R, I pro zobrazení **extrahování rozhraní** dialogové okno.  
  
     Můžete také kliknout pravým tlačítkem myši, přejděte na příkaz **Refaktorovat**a potom klikněte na **extrahování rozhraní** zobrazíte **extrahování rozhraní** dialogové okno.  
  
3.  Klikněte na tlačítko **Vybrat vše**.  
  
4.  Click **OK**.  
  
     Zobrazí nový soubor, IProtoA.cs a následující kód:  
  
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
 Tato funkce je dostupné, pouze pokud kurzor je nastavený v třída, struktura nebo rozhraní, které obsahuje členy, které mají být extrahovány. Pokud se ukazatel na této pozici, vyvolání operace refaktoringu extrahování rozhraní.  
  
 Při vyvolání extrahování rozhraní na třídu nebo na struktury seznamu základů a rozhraní je upravit tak, aby zahrnují nový název rozhraní. Při vyvolání extrahování rozhraní na rozhraní, seznamu základů a rozhraní se nemění.  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](refactoring-csharp.md)