---
redirect_url: /visualstudio/csharp-ide/refactoring/change-method-signature
title: "Refaktoring (C#) pro odebrání parametrů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.csharp.refactoring.remove
dev_langs: CSharp
helpviewer_keywords:
- parameters [C#], removing
- refactoring [C#], Remove Parameters
- Remove Parameters refactoring [C#]
ms.assetid: f4fc3265-0ef8-4398-a691-c338178697a6
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 549914476db028cc5135de3c954ac841ab2da628
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="remove-parameters-refactoring-c"></a>Refaktoring pro odebrání parametrů (C#)
`Remove Parameters`je operace refaktoringu, která poskytuje snadný způsob, jak odebrat parametry z metod, indexery a delegáti. Odebrání parametrů změny deklaraci; na všech umístěních, kde je volán člen odeberou se tak, aby odrážely novou deklaraci parametru.  
  
 Při provádění operace odebrat parametry tak, že první umístíte kurzor na metodu, indexer nebo delegáta. Při kurzor se nachází v pozici k vyvolání odebrat `Parameters` operace, klikněte **Refaktorovat** nabídky, stiskněte klávesovou zkratku, nebo v místní nabídce vyberte příkaz.  
  
> [!NOTE]
>  První parametr nejde odebrat v metody rozšíření.  
  
### <a name="to-remove-parameters"></a>Chcete-li odebrat parametry  
  
1.  Vytvořte konzolovou aplikaci s názvem `RemoveParameters`a potom můžete nahradit `Program` následujícím kódem.  
  
    ```csharp  
    class A  
    {  
        // Invoke on 'A'.  
        public A(string s, int i) { }  
    }  
  
    class B  
    {  
        void C()  
        {  
            // Invoke on 'A'.  
            A a = new A("a", 2);  
        }  
    }  
    ```  
  
2.  Umístěte kurzor na metoda `A`, buď v deklarace metody nebo volání metody.  
  
3.  Z **Refaktorovat** nabídce vyberte možnost **odebrat parametry** zobrazíte **odebrat parametry** dialogové okno.  
  
     Můžete také zadat klávesovou zkratku CTRL + R V zobrazíte **odebrat parametry** dialogové okno.  
  
     Můžete také kliknout pravým tlačítkem kurzor, přejděte na příkaz **Refaktorovat**a potom klikněte na **odebrat parametry** zobrazíte **odebrat parametry** dialogové okno.  
  
4.  Pomocí **parametry** pole, umístěte kurzor na `int i`a potom klikněte na **odebrat**.  
  
5.  Click **OK**.  
  
6.  V **zobrazení náhledu změn – odebrat parametry** dialogové okno, klikněte na tlačítko **použít**.  
  
## <a name="remarks"></a>Poznámky  
 Parametry můžete odebrat z deklarace metody nebo volání metody. Umístěte kurzor do pole Název metody prohlášení nebo delegáta a vyvolání odebrat parametry.  
  
> [!CAUTION]
>  Odebere parametry umožňuje odebrat parametr, který se odkazuje v těle člena, ale neodebere odkazy na tento parametr v těle metoda. To můžete zavést chyby sestavení do vašeho kódu. Můžete však použít **zobrazení náhledu změn** dialogové okno Kontrola kódu před provedením operace refaktoringu.  
  
 Pokud je parametr, který je právě odebírán změně během volání do metody, odebrání parametru budou odebrány také úpravy. Například jestli volání metody se změnil z  
  
```csharp  
MyMethod(param1++, param2);  
```  
  
 až  
  
```csharp  
MyMethod(param2);  
```  
  
 pomocí operace refaktoringu `param1` nebude se zvýší.  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](refactoring-csharp.md)