---
title: Ladění skriptů na straně klienta | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], client-side scripts
- client-side scripts, debugging
ms.assetid: bb668527-2288-47bd-a6c8-cecbad76dde2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6db58ee98ffded99ac9eeaa790f9f255842b5905
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="client-side-script-debugging"></a>Ladění skriptů na straně klienta
Ladicí program Visual Studio poskytuje všestranné prostředí pro vyhledávání a opravy chyb v skripty na straně klienta na stránkách ASP.NET.  
  
## <a name="opening-script-documents"></a>Otevírání dokumentů skriptu  
Zobrazí se seznam dokumenty skript na straně serveru a na straně klienta v **Průzkumníku řešení** k zobrazení. Můžete otevřít skript dokumentu z **Průzkumníku řešení**. Další informace najdete v tématu [postupy: zobrazení dokumentů skriptu](../debugger/how-to-view-script-documents.md).  
  
## <a name="breakpoint-mapping"></a>Mapování zarážek  
 V sadě Visual Studio nelze přímo ladění kódu na straně serveru, ale můžete nastavit zarážky v souboru na straně serveru. Visual Studio automaticky zarážce se mapuje na odpovídající umístění v souboru na straně klienta a vytvoří mapovaná zarážky v kódu na straně klienta.  
  
## <a name="manually-or-automatically-attaching-to-script"></a>Ručně nebo automaticky připojení ke skriptu  
 Chcete-li začít ladění skriptu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], musíte připojit ladicí program ke skriptu, kterou chcete ladit. Tato situace může nastat, ručně nebo automaticky.  
  
 Můžete ručně připojte pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zvolte spuštěných procesů skriptu, kterou chcete připojit k rozhraní ladicího programu. Další informace najdete v tématu [postupy: připojení ke skriptu](../debugger/how-to-attach-to-script.md).  
  
 Ladicí program se automaticky připojí k skriptu při jedné z následujících akcí:  
  
-   Kliknutí na zarážku nastavit ve skriptu.  
  
-   Dosáhl VBScript `Stop` příkaz nebo JScript `debugger` příkaz ve skriptu kódu.  
  
-   Prohlížeč nebo server zaznamená syntaxi nebo Chyba při spuštění ve vašem skriptu. V takovém případě se zobrazí dialogové okno a můžete začít ladění.  
  
 Když ručně připojení ke skriptu, nadále se proces skript spustit, dokud je nějakým způsobem zastavit. Zastavit je tak, že zvolíte **rozdělit** na **ladění** nabídky.  
  
 Když ladicí program automaticky připojí, je na řádku zastavit provádění skriptu kde zarážek, `Stop` příkaz nebo `debugger` příkaz nebo Chyba k chybě, nebo v okamžiku, kdy jste se rozhodli spustit ladění – v aplikaci Internet Explorer.  
  
 V tomto okamžiku můžete zařízení normální ladicí program zahájíte ladění. Například můžete použít **krok** příkazy pokračujte ke spouštění vašeho kódu řádek po řádku. Můžete použít **zásobníkem volání** skript časové období pro zobrazení a řízení toku. Můžete použít proměnné windows nebo **Immediate** okno zobrazení nebo změna proměnných a vlastností.  
  
## <a name="enhanced-error-messages-for-script-debugging"></a>Rozšířené chybové zprávy pro ladění skriptů  
 Visual Studio poskytuje rozšířené chybové zprávy pro ladění problémů běžné skriptů. Tyto zprávy se nezobrazí, dokud ručně připojit k aplikaci Internet Explorer. Pokud dojde k chybový stav při Internet Explorer se automaticky otevře, zkuste ručně připojení tak, aby se zobrazí chybové zprávy.  
  
## <a name="debugging-ajax-script-applications"></a>Ladění aplikací skript AJAX  
 Webové aplikace technologie AJAX hodně využívají kód skriptu a představovat speciální ladění problémů. Informace o techniky ladění AJAX najdete v tématu  
  
 [Ladění a trasování – přehled aplikace Ajax](http://msdn.microsoft.com/Library/92684ea0-7bb4-4a34-9203-3aa6394ce375).  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Omezení ladění skriptů](../debugger/limitations-on-script-debugging.md)   
 [Okna proměnných](../debugger/debugger-windows.md)   
 [Příkazové podokno](../ide/reference/immediate-window.md)   
 [Ladění a trasování – přehled Ajax aplikací](http://msdn.microsoft.com/Library/92684ea0-7bb4-4a34-9203-3aa6394ce375)
