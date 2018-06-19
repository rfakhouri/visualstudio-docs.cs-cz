---
title: Pomocí prostředí Windows Runtime v jazyce JavaScript | Microsoft Docs
ms.custom: ''
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c81f5d83056ceb87987e263f09c0d5e5017dbb6f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792033"
---
# <a name="using-the-windows-runtime-in-javascript"></a>Pomocí prostředí Windows Runtime v jazyce JavaScript
Při psaní aplikace univerzální platformu Windows (UWP), můžete použít prostředí Windows Runtime tříd, metod a vlastností mnohem stejným způsobem, že použijete nativních objektů jazyka JavaScript, metod a vlastností. Toto téma obsahuje úvodní informace a odkazy na témata, která vysvětlují základní koncepce pomocí rozhraní API systému Windows Runtime v jazyce JavaScript, včetně vysvětlení typy prostředí Windows Runtime zastoupení, jak používat asynchronních metod prostředí Windows Runtime a jak poslech a zpracování událostí prostředí Windows Runtime.  
  
 Můžete najít referenční dokumentace jazyka JavaScript v [referenční dokumentace jazyka JavaScript](../javascript/javascript-language-reference.md).  
  
> [!IMPORTANT]
>  Prostředí Windows Runtime funkcí nejsou k dispozici pro aplikace, které běží v aplikaci Internet Explorer.  
  
## <a name="windows-runtime-reference-documentation"></a>Windows Runtime referenční dokumentaci k nástroji  
 Referenční dokumentaci najdete v tématu [Windows Runtime odkaz](https://msdn.microsoft.com/en-us/library/windows/apps/br211377.aspx). Příklady kódu jsou dostupné v jazyce JavaScript a také v C++, C# a Visual Basic.  
  
## <a name="writing-windows-runtime-components-in-c-c-or-visual-basic"></a>Zápis součásti systému Windows Runtime v C++, C# nebo Visual Basic  
 Pokyny a pokyny pro tvorbu prostředí Windows Runtime součásti, které mohou být využívány v jazyce JavaScript naleznete v tématu [vytváření součásti systému Windows Runtime v jazyce C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp) a [vytváření součásti systému Windows Runtime v C# a Visual Základní](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).  
  
## <a name="casing-conventions-with-windows-runtime-features"></a>Konvence velká a malá písmena s funkcí Windows Runtime  
 Konvence velká a malá písmena pro prostředí Windows Runtime funkce v jazyce JavaScript mírně lišit od těch, které pro jiné jazyky:  
  
-   Obory názvů a třídy se nacházejí v pascalcase:  
  
    ```JavaScript  
    Windows.Deployment.PackageInfo;  
    ```  
  
-   Členy třídy, včetně metody a vlastnosti a členové struktury a výčty, jsou v camelCase:  
  
    ```JavaScript  
    Deployment.PackageInfo.createPackage();  
    ```  
  
-   Názvy událostí jsou v malá písmena:  
  
    ```JavaScript  
    dataTransferManager.ontargetapplicationchosen;  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Informace týkající se použití prostředí Windows Runtime rozhraní API](../jswinrt/considerations-when-using-the-windows-runtime-api.md)   
 [Použití asynchronních metod Windows Runtime](../jswinrt/using-windows-runtime-asynchronous-methods.md)   
 [Zpracování událostí Windows Runtime v jazyce JavaScript](../jswinrt/handling-windows-runtime-events-in-javascript.md)   
 [Reprezentace JavaScript Runtime typy systému Windows](../jswinrt/javascript-representation-of-windows-runtime-types.md)   
 [Projekce JavaScript Windows Runtime data a času a časového rozpětí](../jswinrt/windows-runtime-datetime-and-timespan-representations.md)