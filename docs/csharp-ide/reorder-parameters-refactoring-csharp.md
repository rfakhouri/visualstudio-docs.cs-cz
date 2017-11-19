---
redirect_url: /visualstudio/csharp-ide/refactoring/change-method-signature
title: "Refaktoring přeskupení parametrů (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.csharp.refactoring.reorder
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Reorder Parameters
- Reorder Parameters refactoring [C#]
ms.assetid: 4dabf21a-a9f0-41e9-b11b-55760cf2bd90
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3469e9ae7101c9e180fba5558fce389c6dfcc72d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="reorder-parameters-refactoring-c"></a>Refaktoring přeskupení parametrů (C#)
`Reorder Parameters`je Visual C# refaktoring operaci, která poskytuje snadný způsob, jak změnit pořadí parametrů pro metody, indexery a delegáti. `Reorder Parameters`změny prohlášení, a na všech umístěních, kde je volán člen, jsou přeskupení parametrů tak, aby odrážely novou pořadí.  
  
 K provedení `Reorder Parameters` operace, umístěte kurzor na nebo vedle metoda, indexer nebo delegáta. Pokud se ukazatel v pozici, vyvolání `Reorder Parameters` operace stisknutím klávesové zkratky, nebo klikněte na příkaz v místní nabídce.  
  
> [!NOTE]
>  První parametr metody rozšíření nelze změnit pořadí.  
  
### <a name="to-reorder-parameters"></a>Změna pořadí parametrů  
  
1.  Vytvoření knihovny tříd s názvem `ReorderParameters`a potom můžete nahradit `Class1` s následující příklad kódu.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  Umístěte kurzor na `MethodB`, buď v deklarace metody nebo volání metody.  
  
3.  Na **Refaktorovat** nabídky, klikněte na tlačítko **Změna pořadí parametrů**.  
  
     **Změna pořadí parametrů** zobrazí se dialogové okno.  
  
4.  V **Změna pořadí parametrů** dialogové okno, vyberte `int i` v **parametry** seznamu a pak klikněte na tlačítko dolů.  
  
     Alternativně můžete přetáhnout `int i` po `bool b` v **parametry** seznamu.  
  
5.  V **Změna pořadí parametrů** dialogové okno, klikněte na tlačítko **OK**.  
  
     Pokud **zobrazení náhledu změn odkaz** je vybraná možnost v **Změna pořadí parametrů** dialogové okno, **zobrazení náhledu změn - Změna pořadí parametrů** se zobrazí dialogové okno. Poskytuje náhled změny v seznamu parametrů pro `MethodB` v podpisu a volání metody.  
  
    1.  Pokud **zobrazení náhledu změn - Změna pořadí parametrů** se zobrazí dialogové okno, klikněte na tlačítko **použít**.  
  
         V tomto příkladu metoda deklarace a všechny metody volání lokalit pro `MethodB` jsou aktualizovány.  
  
## <a name="remarks"></a>Poznámky  
 Můžete změnit pořadí parametrů z deklarace metody nebo volání metody. Umístěte kurzor na nebo vedle deklaraci metody nebo delegáta, ale není v textu.  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](refactoring-csharp.md)