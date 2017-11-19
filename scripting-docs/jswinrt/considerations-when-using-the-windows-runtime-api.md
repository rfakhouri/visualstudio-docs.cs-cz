---
title: "Informace týkající se použití prostředí Windows Runtime rozhraní API | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 693b3dac9def5533417638c3ec1c0de8db1d5fe3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="considerations-when-using-the-windows-runtime-api"></a>Informace týkající se použití prostředí Windows Runtime rozhraní API
Téměř každý element modulu Runtime rozhraní API systému Windows můžete použít v jazyce JavaScript. Nicméně existují některé aspekty reprezentace JavaScript elementů prostředí Windows Runtime, které byste měli mít na paměti.  
  
> [!IMPORTANT]
>  Informace o vytváření komponent prostředí Windows Runtime v jazyce C++, C# nebo Visual Basic a jejich použití v jazyce JavaScript, najdete v části [vytváření součásti systému Windows Runtime v jazyce C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp) a [vytváření součásti systému Windows Runtime v jazyce C# a Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).  
  
## <a name="special-cases-in-the-javascript-representation-of-windows-runtime-types"></a>Zvláštní případy v reprezentace JavaScript Runtime typy systému Windows  
  
-   Řetězce: Řetězec Neinicializovaný je předaný metodě prostředí Windows Runtime jako řetězec "undefined" a nastavte na řetězec `null` se předá jako řetězec "null". (To platí vždy, když `null` nebo `undefined` sloučen hodnotu na řetězec.) Před řetězec předáte metodě prostředí Windows Runtime, je musí inicializovat jako prázdný řetězec ("").  
  
-   Rozhraní: Nelze implementovat rozhraní prostředí Windows Runtime v jazyce JavaScript.  
  
-   Pole: Prostředí Windows Runtime pole nejsou s možností změny velikosti, tak v prostředí Windows Runtime pole nefungují metody, které změnit velikost pole v jazyce JavaScript.  
  
-   Pole: Pokud předáte hodnotu pole JavaScript na prostředí Windows Runtime metodu, se zkopíruje pole. Metoda prostředí Windows Runtime není možné vrátit zpět do aplikace JavaScript a změňte pole nebo její členy. Můžete však použít typovaná pole (například [int32array – objekt](../javascript/reference/int32array-object.md)), které nejsou zkopírovány.  
  
-   Struktury: Struktury prostředí Windows Runtime jsou objekty v jazyce JavaScript. Pokud chcete předat struktura prostředí Windows Runtime do prostředí Windows Runtime metody, nemáte vytvoření instance struktury s `new` – klíčové slovo. Místo toho vytvořte objekt a přidejte příslušné členy a jejich hodnoty. Názvy členů musí být v camelCase: `SomeStruct.firstMember`.  
  
-   Objekty: JavaScript – objekty nejsou stejná jako objekty spravovaného kódu (`System.Object`). Nelze předat objekt jazyka JavaScript na prostředí Windows Runtime metodu, která vyžaduje `System.Object`.  
  
-   Objekt identity: ve většině případů objekty předávané přepínat mezi prostředí Windows Runtime a JavaScript se nemění. Modul JavaScript udržuje mapu známé objektů. Pokud je vrácen objekt z prostředí Windows Runtime je porovnání mapy a pokud neexistuje nový objekt, který se vytvoří. Stejný postup je pak pro objekty, které představují rozhraní, které se vrátí pomocí prostředí Windows Runtime metody. Existují dva druhy výjimek:  
  
    -   Objekty, které jsou vráceny z prostředí Windows Runtime volat a pak mít přidání nových vlastností (expando), nemáte zachovat jejich nové vlastnosti při jsou předávány zpět do prostředí Windows Runtime. Ale pokud se vrátí do aplikace JavaScript, protože jste namapovat na existující objekt, vráceného objektu mít expando vlastnosti.  
  
    -   Struktury a delegáti v prostředí Windows Runtime nelze identifikovat jako identické dřív používal struktury nebo delegáti. Pokaždé, když se vrátí struktura nebo delegáta, získá nový odkaz.  
  
-   Název kolizí: více prostředí Windows Runtime rozhraní může mít členy se stejnými názvy. Pokud jsou zkombinovány v jednom objektu JavaScript (může to být reprezentace runtime třídy nebo rozhraní), jsou členy reprezentované s plně kvalifikované názvy. Těchto členů můžete volat pomocí následující syntaxe: `Class["MemberName"](parameter)`.  
  
     V následujícím kódu dvě rozhraní se metody kreslení a třídu runtime implementuje obě rozhraní.  
  
    ```cpp#  
    namespace CollisionExample {  
        interface InterfaceA  
        {  
            HRESULT Draw([in] Int32 a);  
        }  
        interface InterfaceB  
        {  
            HRESULT Draw([in] HString a);  
        }  
        runtimeclass ExampleObject {  
          interface InterfaceA  
          interface InterfaceB  
        }  
    }  
    ```  
  
     Zde je, jak můžete volat ve výše uvedeném kódu v jazyce JavaScript.  
  
    ```JavaScript  
    var example = new ExampleObject();  
    example["CollisionExample.InterfaceA.draw"](12);  
    example["CollisionExample.InterfaceB.draw"]("hello");  
    ```  
  
-   `Out`Parametry: Pokud prostředí Windows Runtime metoda obsahuje více `out` parametry, v jazyce JavaScript metoda má objekt jazyka JavaScript jako hodnoty, a objekt vlastnosti, které odpovídají `out` parametr. Zvažte například následující podpis prostředí Windows Runtime v jazyce C++.  
  
    ```cpp#  
    void ExampleMethod(  
      [OutAttribute] char^ first,   
      [OutAttribute] char^ second  
    )  
    ```  
  
     Verze jazyka JavaScript tento podpis je:  
  
    ```JavaScript  
    var returnValue = exampleMethod();  
  
    ```  
  
     V tomto příkladu `returnValue` se objekt jazyka JavaScript, která má dvě pole: `first` a `second`.  
  
-   Statické členy: prostředí Windows Runtime definuje statické členy a členů instance. V jazyce JavaScript jsou statické členy přidat k objektu, který je přidružen prostředí Windows Runtime třídy nebo rozhraní.  
  
    ```JavaScript  
    // Static method.   
    var accel = Windows.Devices.Sensors.Accelerometer.getDefault();   
    // Instance method.   
    var reading = accel.getCurrentReading();            
    ```  
  
 Další informace o JavaScript reprezentace základní typy prostředí Windows Runtime najdete v tématu [JavaScript reprezentace Runtime Windows typy](../jswinrt/javascript-representation-of-windows-runtime-types.md).