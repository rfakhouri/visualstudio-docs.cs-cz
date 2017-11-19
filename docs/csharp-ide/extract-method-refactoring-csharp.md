---
redirect_url: /visualstudio/csharp-ide/refactoring/extract-method
title: "Extrahování metody refaktoring (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Extract Method
- Extract Method refactoring operation [C#]
ms.assetid: eeba11df-a815-4bec-9c21-8a831891b783
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e85e745241d8fa880098b73a6306cbca3f19da70
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="extract-method-refactoring-c"></a>Refaktoring pro extrahování metody (C#)
**Extrahování metody** je operace refaktoringu, která poskytuje snadný způsob, jak vytvořit novou metodu z fragment kódu v existujícího člena.  
  
 Pomocí **extrahovat metodu**, můžete vytvořit nová metoda extrahování výběr kód z uvnitř bloku kódu z existujícího člena. Metoda nové, extrahované obsahuje vybraný úsek kódu a na vybraný úsek kódu v existujícího člena je nahrazena volání nové metody. Když fragment kódu do své vlastní metoda vám umožní rychle a přesně reorganizovat kód pro lepší čitelnost a opakované použití.  
  
 **Extrahování metody** má následující výhody:  
  
-   Podporuje postupy nejvhodnější kódování podle zdůraznění diskrétní, opakovaně použitelný metody.  
  
-   Umožňuje samoobslužné dokumentace kódu prostřednictvím dobrý organizace.  
  
     Při popisné názvy jsou použité, vysoké úrovně metody víc jako řadu komentáře.  
  
-   Podporuje vytváření metod citlivější zjednodušit přepsání.  
  
-   Snižuje zdvojení kódu.  
  
### <a name="to-use-extract-method"></a>Použití extrahování metody  
  
1.  Vytvořte konzolovou aplikaci s názvem `ExtractMethod`a potom můžete nahradit `Program` s následující příklad kódu.  
  
    ```csharp  
    class A  
    {  
        const double PI = 3.141592;  
  
        double CalculatePaintNeeded(double paintPerUnit, double radius)  
        {  
            // Select any of the following:  
            // 1. The entire next line of code.  
            // 2. The right-hand side of the next line of code.  
            // 3. Just "PI *" of the right-hand side of the next line  
            //    of code (to see the prompt for selection expansion).  
            // 4.  All code within the method body.  
            // ...Then invoke Extract Method.  
  
            double area = PI * radius * radius;  
  
            return area / paintPerUnit;  
        }  
    }  
    ```  
  
2.  Vyberte, které mají být extrahovány fragment kódu:  
  
    ```csharp  
    double area = PI * radius * radius;  
    ```  
  
3.  Na **Refaktorovat** nabídky, klikněte na tlačítko **extrahovat metodu**.  
  
     **Extrahovat metodu** zobrazí se dialogové okno.  
  
     Alternativně můžete také zadat klávesovou zkratku CTRL + R, M zobrazíte **extrahovat metodu** dialogové okno.  
  
     Můžete můžete také kliknout pravým tlačítkem vybrané kódu, přejděte na příkaz **Refaktorovat**a potom klikněte na **extrahovat metodu** zobrazíte **extrahovat metodu** dialogové okno.  
  
4.  Zadejte název nové metody, jako například `CircleArea`v **nový název metody** pole.  
  
     Náhled nové podpis metody zobrazí v části **podpis metody Preview**.  
  
5.  Click **OK**.  
  
## <a name="remarks"></a>Poznámky  
 Při použití **extrahovat metodu** příkaz, je nová metoda vložit členem zdroje ve stejné třídě.  
  
## <a name="partial-types"></a>Částečné typy  
 Pokud je třída částečné typu, pak **extrahovat metodu** vygeneruje nová metoda hned za zdrojový člen. **Extrahování metody** Určuje podpis nové metody, pokud žádná data instance odkazuje kód do nové metody vytváření statickou metodu.  
  
## <a name="generic-type-parameters"></a>Parametry obecného typu  
 Při extrahování metodu, která má parametr obecného typu neomezeným generovaný kód nepřidá `ref` modifikátor tento parametr Pokud hodnota je k němu přiřazen. Pokud extrahované metoda bude podporovat odkazové typy jako argument obecného typu, pak byste měli přidat ručně `ref` modifikátor na parametr v podpis metody.  
  
## <a name="anonymous-methods"></a>Anonymní metody  
 Pokud se pokusíte extrahovat část anonymní metoda, která obsahuje odkaz na místní proměnné, která je buď deklarován nebo je odkazované mimo metodu anonymní, pak Visual Studio bude vás upozorní na potenciální sémantickými změnami.  
  
 Pokud anonymní metoda používá hodnotu místní proměnné, je hodnota získat v okamžiku, kdy anonymní metody. Při anonymní metody je extrahován do jiné metody, je v tuto chvíli volání metody extrahované získat hodnoty místní proměnné.  
  
 Následující příklad ilustruje této sémantického změny. Pokud tento kód spuštěn, pak **11** vytiskne se ke konzole. Pokud používáte **extrahovat metodu** k extrahování oblasti kódu, která je označena kvalifikátorem komentáře kódu do své vlastní metody a pak spustit refactored kód, pak **10** vytiskne se ke konzole.  
  
```csharp  
class Program  
{  
    delegate void D();  
    D d;  
    static void Main(string[] args)  
    {  
        Program p = new Program();  
        int i = 10;  
        /*begin extraction*/  
            p.d = delegate { Console.WriteLine(i++); };  
        /*end extraction*/  
        i++;  
        p.d();  
    }  
}  
```  
  
 K této situaci vyřešit, zkontrolujte místní proměnné, které se používají v polích anonymní metody třídy.  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](refactoring-csharp.md)