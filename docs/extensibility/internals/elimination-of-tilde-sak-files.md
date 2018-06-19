---
title: Odstranění ~ SAK soubory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- temporary files
- ~sak files
- source control plug-ins, ~SAK files
ms.assetid: 5277b5fa-073b-4bd1-8ba1-9dc913aa3c50
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 61227652bf191280f69466f127c4a400ea43856e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129638"
---
# <a name="elimination-of-sak-files"></a>Odstranění ~ SAK soubory
1.2 rozhraní API modulu Plugin zdroj ovládacího prvku ~ SAK soubory byly nahrazeny schopností příznaky a nové funkce, která zjišťují, jestli podporuje modul plug-in správy zdroje MSSCCPRJ souborů a sdílené rezervace.  
  
## <a name="sak-files"></a>~ SAK soubory  
 Visual Studio .NET 2003 vytvořit dočasné soubory s předponou ~ SAK. Tyto soubory se používají k určení, jestli podporuje modul plug-in správy zdroje:  
  
-   MSSCCPRJ. SCC soubor.  
  
-   Více rezervace (sdílené).  
  
 Pro moduly plug-in, které podporují pokročilé funkce zadaný v rozhraní API 1.2 zdroj ovládacího prvku Plug-in IDE, můžete zjistit tyto funkce bez vytváření dočasných souborů pomocí nové funkce, příznaky a funkce, které jsou podrobně popsané v následujících částech.  
  
## <a name="new-capability-flags"></a>Nové funkce příznaky  
 `SCC_CAP_SCCFILE`  
  
 `SCC_CAP_MULTICHECKOUT`  
  
## <a name="new-functions"></a>Nové funkce  
 [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md)  
  
 [SccIsMultiCheckoutEnabled](../../extensibility/sccismulticheckoutenabled-function.md)  
  
 Pokud modul plug-in správy zdroje podporuje více rezervace (sdílené), pak deklaruje `SCC_CAP_MULTICHECKOUT` schopnosti a implementuje `SccIsMultiCheckOutEnabled` funkce. Tato funkce je volána, když najdete v článku věnovaném operace proběhne žádným z projektů řízené zdroje.  
  
 Pokud modul plug-in správy zdroje podporuje vytváření a používání MSSCCPRJ. Deklaruje SCC souboru a potom `SCC_CAP_SCCFILE` schopnosti a implementuje [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md). Tato funkce je volána s seznam souborů. Funkce vrátí hodnotu `TRUE/FALSE` pro každý soubor indikující, zda Visual Studio se má použít MSSCCPRJ. Soubor SCC pro ni. Pokud modul plug-in správy zdroje nezobrazovat se podporují tyto nové funkce a funkce, může použít následující klíč registru zakázat vytvoření těchto souborů:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateTemporaryFilesInSourceControl" = dword: 00000001  
  
> [!NOTE]
>  Pokud tento klíč registru je nastavené na DWORD: 00000000, je ekvivalentní klíč se neexistující a Visual Studio pořád se pokouší o vytvoření dočasné soubory. Ale pokud DWORD: 00000001 nastavení klíče registru, Visual Studio nebude pokoušet vytvořit dočasné soubory. Místo toho předpokládá, že modul plug-in správy zdroje nepodporuje MSSCCPRJ. Soubor SCC a nepodporuje sdílené rezervace.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)