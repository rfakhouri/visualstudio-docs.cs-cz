---
title: "Jazyk služeb a editoru základní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - language services
ms.assetid: e03199a6-ad5f-4075-bfba-8d36865112b7
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c3d2bcad21bb919125b487a57b73d3a458a3a1f9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="language-services-and-the-core-editor"></a>Jazyk služeb a editoru jádra
Editory v sadě Visual Studio jsou často přidružená služba jazyka. Kromě jiných věcí poskytuje služba jazyka barevné zvýrazňování syntaxe, dokončování příkazů, IntelliSense a formátování textu.  
  
## <a name="core-editors-and-document-data-objects"></a>Editory jádra a datové objekty dokumentu  
 Při přístupu k editoru základní nevytvoříte dokumentu data a objekty zobrazení dokumentu. Prostředí IDE vytvoří a ovládací prvky tyto dva objekty a obslužné rutiny k nim získáte tak, že příslušná volání ve svém editoru implementace objektu factory.  
  
 Další informace najdete v tématu [určení Editor, který otevře soubor v projektu](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md).  
  
## <a name="language-services-and-the-core-editor"></a>Jazyk služeb a editoru jádra  
 Implementací služba jazyka můžete řídit způsob zobrazení dat v zobrazení dokumentu. Služba jazyka poskytuje informace a chování, které jsou specifické pro daný jazyk, jako je například Visual C++. Při vytváření textovou vyrovnávací paměť a určit příponu názvu souboru pro dokument, který chcete otevřít, textové vyrovnávací paměti určuje jazyk služby přidružené k této příponu názvu souboru z klíče registru, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Editors \\\Extensions {YourLanguageService GUID}. Standardní VSPackage načítání postup potom načte vaše VSPackage a vytvoření instance služby jazyk.  
  
 Služba základní jazyka je vidět na následujícím obrázku.  
  
 ![Jazyk modelu služby obrázek](../extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
Objekty služby základní editoru a jazyk  
  
 Datový objekt dokumentu pro editor základní se označuje jako textovou vyrovnávací paměť a je reprezentována <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objektu. Objekt zobrazení dokumentu se nazývá textového zobrazení a je reprezentována <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> objektu. Tyto dva objekty spolupracovat prostřednictvím služby jazyk poskytnout jednotný pohled na editoru jádra. Informace z textová vyrovnávací paměť a zobrazí zobrazení textu v okně dokumentu volá okno kódu. Okna dokumentu kód spravuje správce okno kódu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 [Poskytuje služby kontextu jazyka pomocí starší verze rozhraní API](../extensibility/providing-a-language-service-context-by-using-the-legacy-api.md)   
 [Hostování IntelliSense](../extensibility/intellisense-hosting.md)   
 [Obsažené jazyky](../extensibility/contained-languages.md)   
 [Vývoj služby starší verze jazyka](../extensibility/internals/developing-a-legacy-language-service.md)