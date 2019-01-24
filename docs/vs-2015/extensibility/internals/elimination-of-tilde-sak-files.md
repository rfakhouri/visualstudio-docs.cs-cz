---
title: Odstranění ~ SAK souborů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- temporary files
- ~sak files
- source control plug-ins, ~SAK files
ms.assetid: 5277b5fa-073b-4bd1-8ba1-9dc913aa3c50
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 70efef9232bd7e9baf317e59111e59e9f98bf46b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760867"
---
# <a name="elimination-of-sak-files"></a>Odstranění souborů ~SAK
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Zdrojový ovládací prvek modulu Plug-in API 1.2 ~ SAK soubory byly nahrazeny příznaky funkcí a nových funkcí, které zjišťují, jestli podporuje MSSCCPRJ souborové služby a sdílenými registracemi plug-in správy zdrojových kódů.  
  
## <a name="sak-files"></a>~ Souborů SAK  
 Visual Studio .NET 2003 vytvoření dočasných souborů s předponou ~ SAK. Tyto soubory se používají k určení, jestli podporuje modul plug-in správy zdrojového kódu:  
  
- MSSCCPRJ. SCC souboru.  
  
- Více (sdílené) rezervace.  
  
  Pro moduly plug-in, které podporují pokročilé funkce, které jsou k dispozici v rozhraní API 1.2 zdrojový ovládací prvek modulu Plug-in rozhraní IDE dokáže tyto možnosti bez vytvoření dočasných souborů pomocí nové možnosti, příznaky a funkce, které jsou podrobně popsané v následujících částech.  
  
## <a name="new-capability-flags"></a>Nové příznaky funkcí  
 `SCC_CAP_SCCFILE`  
  
 `SCC_CAP_MULTICHECKOUT`  
  
## <a name="new-functions"></a>Nové funkce  
 [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md)  
  
 [SccIsMultiCheckoutEnabled](../../extensibility/sccismulticheckoutenabled-function.md)  
  
 Pokud více rezervace (sdílené) podporuje modul plug-in správy zdrojového kódu, pak deklaruje `SCC_CAP_MULTICHECKOUT` funkce a implementuje `SccIsMultiCheckOutEnabled` funkce. Tato funkce je volána pokaždé, když probíhá operace rezervace na kterýkoli z projektů se spravovanými zdroji.  
  
 Pokud modul plug-in správy zdrojových kódů podporuje vytváření a využívání MSSCCPRJ. Deklaruje SCC souboru a pak `SCC_CAP_SCCFILE` funkce a implementuje [sccwillcreatesccfile –](../../extensibility/sccwillcreatesccfile-function.md). Tato funkce je volána s seznam souborů. Funkce vrátí `TRUE/FALSE` pro každý soubor k označení, zda sada Visual Studio by měl používat MSSCCPRJ. Soubor SCC pro něj. Pokud se rozhodne modul plug-in správy zdrojového kódu není pro podporu těchto nových funkcí a funkcí, ho můžete použít následující klíč registru zakázat vytvoření těchto souborů:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateTemporaryFilesInSourceControl"=dword:00000001  
  
> [!NOTE]
>  Pokud tento klíč registru DWORD: 00000000, odpovídá klíči se neexistující a sady Visual Studio dál pokoušet o vytvoření dočasné soubory. Nicméně pokud DWORD: 00000001 nastavení klíče registru, Visual Studio nebude pokoušet o vytvoření dočasné soubory. Místo toho předpokládá, že modul plug-in správy zdrojového kódu není podporováno MSSCCPRJ. Soubor SCC a sdílenými registracemi nepodporuje.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)
