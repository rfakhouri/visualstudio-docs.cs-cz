---
title: "Příprava na ladění: Projekty konzoly | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], console applications
- debugging console applications
- console applications, debugging
ms.assetid: 9641f1d9-2d5a-48b1-8731-6525e8f67892
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9e1ade672c3abd81f4f71d1e48a39560e17e1465
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-preparation-console-projects"></a>Příprava ladění: projekty konzoly
Příprava na ladění projektu pro konzoly je podobná Příprava na ladění projektu pro Windows, se některé další aspekty. Další informace najdete v tématu [aplikacích Windows Forms](../debugger/debugging-preparation-windows-forms-applications.md), a [Příprava ladění: Windows Forms aplikace (.NET)](http://msdn.microsoft.com/en-us/a8bc54de-41a3-464d-9a12-db9bdcbc1ad5). Z důvodu podobnosti všechny aplikace konzoly Toto téma obsahuje následující typy projektů:  
  
-   Konzolovou aplikaci C#  
  
-   Konzolové aplikace jazyka Visual Basic  
  
-   C++ konzolové aplikace (.NET)  
  
-   Aplikace C++ konzoly (Win32)  
  
 Možná budete muset zadat argumenty příkazového řádku pro konzolové aplikace. Další informace najdete v tématu [nastavení projektu pro konfiguraci ladění C++](../debugger/project-settings-for-a-cpp-debug-configuration.md), [nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), nebo [nastavení projektu pro ladění konfigurace C# ](../debugger/project-settings-for-csharp-debug-configurations.md).  
  
 Jako projektu všechny vlastnosti, tyto argumenty zachování mezi ladicí relace a mezi relacemi sady Visual Studio. Proto pokud konzolové aplikace, který jste dříve ladit, mějte na paměti, že může být argumenty z předchozí relace zadané v  **\<Projekt > stránky vlastností** dialogové okno.  
  
 Využívá konzolovou aplikaci **konzoly** okna tak, aby přijímal vstup a výstup zprávy o zobrazení. Zapsat do **konzoly** okno, musí vaše aplikace používat **konzoly** objektu namísto objektu Debug. Zapsat do **Visual Studio výstup** okně použít objekt ladění jako obvykle. Ujistěte se, že víte, kde vaše aplikace je zápis nebo hledáte může být zprávy nesprávné místo. Další informace najdete v tématu [konzoly třída](/dotnet/api/system.console), [ladění třída](/dotnet/api/system.diagnostics.debug), a [výstup – okno](../ide/reference/output-window.md).  
  
## <a name="starting-the-application"></a>Spouštění aplikace  
 Při spuštění některé aplikace konzoly, spustit na dokončení a poté ukončete. Toto chování nemusí poskytnout dostatek času k přerušení spuštění a ladění. Abyste mohli k ladění aplikace, použijte jednu z následujících postupů a spusťte aplikaci:  
  
-   Vaše aplikace spustí, provádění a běží, dokud nebude dosaženo zarážce.  
  
-   Vaše aplikace spustí a okamžitě dělí na první řádek zdrojového kódu.  
  
-   V okně zdrojového kódu, klikněte pravým tlačítkem na řádku a vyberte **spustit ke kurzoru**.  
  
     Aplikace spustí a spustí vybraného řádku, nebo zarážku, pokud je průchodu zarážkou před řádek.  
  
 Při ladění aplikace konzoly, můžete chtít spustit aplikaci z příkazového řádku a nikoli ze sady Visual Studio. V takovém případě můžete spustit aplikaci z příkazového řádku a k němu připojí ladicí program Visual Studio. Další informace najdete v tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
 Při spuštění aplikace konzoly ze sady Visual Studio **konzoly** někdy okno za okno sady Visual Studio. Pokud se pokusíte spustit Konzolová aplikace z Visual Studia a nic zdá se, že dojít, přesouvání okně Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Typy projektů Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)