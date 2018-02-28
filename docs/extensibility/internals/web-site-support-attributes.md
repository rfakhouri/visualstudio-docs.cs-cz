---
title: "Webové stránky podpory atributy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 868fe0785c90a174610b9fff837fc6fbfb084e83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="web-site-support-attributes"></a>Atributy webu podpory
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Webový projekt lze rozšířit zajistit podporu pro webové programovacích jazyků. Jazyk musí se registrovat s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tak, aby šablony projektů může vyskytovat v **nový web** dialogové okno když je vybraný jazyk.  
  
 Ukázka IronPython Studio zahrnuje podporu webu. Obsahuje následující třídy atributů k registraci IronPython jako codebehind jazyk pro nové webové projekty.  
  
## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute  
 Tento atribut je umístěn na projekt jazyka. Jazyk ho přidá do seznamu webových programovacích jazyků v **jazyk** v seznamu **nový web** dialogové okno. Například následující přidá IronPython do seznamu:  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Tento atribut nastaví také cestu šablony tak, aby odkazoval na složku šablony. Další informace o umístění složky šablony najdete v tématu [webu podpory šablony](../../extensibility/internals/web-site-support-templates.md).  
  
## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute  
 Tento atribut je umístěn na projekt jazyka. Webový projekt lze vnořit jeden typ souboru (souvisejících) umožňuje v rámci jiného typu souboru (primární) v **Průzkumníku řešení**.  
  
 Příklad:  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Určuje, že soubor codebehind IronPython vztahuje na soubor .aspx. Při vytvoření nové webové stránky .aspx v řešení lokality IronPython webové nový soubor .py zdroje se vygeneruje a zobrazí se jako podřízený uzel stránky .aspx.  
  
## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute  
 Tento atribut je umístěn na jazykovou sadu projektu. Vybere poskytovatele Intellisense pro jazyk.  
  
 Příklad:  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 Určuje, že instance PythonIntellisenseProvider, která implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, by se měl vytvořit na vyžádání k poskytování služeb jazyk.  
  
 Implementace IVsIntellisenseProject zpracovává odkazy a volá kompilátor jazyka, pokud webové stránky s kódem je požadována, ale není v mezipaměti.  
  
## <a name="see-also"></a>Viz také  
 [Podpora webu](../../extensibility/internals/web-site-support.md)