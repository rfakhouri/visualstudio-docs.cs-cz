---
title: Atributy podpory webu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 75401eb0d5acd5d363d05aec57909eef5b9855e3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68144300"
---
# <a name="web-site-support-attributes"></a>Atributy podpory webu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Webový projekt je možné rozšířit o podporu pro webové programovacích jazyků. Jazyk musí registrovat s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tak, aby šablony projektů mohou objevit v **nový web** dialogové okno při výběru jazyka.  
  
 Ukázka IronPython Studio zahrnuje podporu webu. Můžete ho najít [VSSDK ukázky](../../misc/vssdk-samples.md). Obsahuje následující třídy atributů k registraci Ironpythonu jako codebehind jazyk pro nové webové projekty.  
  
## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute  
 Tento atribut je umístěn v projektu jazyka. Přidá jazyk na seznam programovacích jazyků v oddílu Web **jazyk** v seznamu **nový web** dialogové okno. Například následující přidá IronPython do seznamu:  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Tento atribut nastaví také šablony cesty tak, aby odkazoval do složky šablony. Další informace o umístění složky šablony najdete v tématu [šablony podpory webu](../../extensibility/internals/web-site-support-templates.md).  
  
## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute  
 Tento atribut je umístěn v projektu jazyka. Webový projekt vnořit jeden typ souboru (související) umožňuje v rámci jiného typu souboru (primární) v **Průzkumníka řešení**.  
  
 Příklad:  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Určuje, že soubor codebehind Ironpythonu vztahuje na soubor .aspx. Při vytvoření nové webové stránky .aspx v Ironpythonu webového řešení lokality nový zdrojový soubor .py se vygeneruje a zobrazí se jako podřízený uzel stránky ASPX.  
  
## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute  
 Tento atribut je umístěn na balíčku projektu jazyka. Vybere poskytovatele technologie Intellisense pro jazyk.  
  
 Příklad:  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 Určuje, že instance PythonIntellisenseProvider, která implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, by měl být vytvořen na vyžádání k poskytování služeb jazyka.  
  
 Implementace IVsIntellisenseProject zpracovává odkazy a volá kompilátor jazyka, pokud webové stránky s kódem je požadováno, ale neukládá do mezipaměti.  
  
## <a name="see-also"></a>Viz také  
 [Podpora webu](../../extensibility/internals/web-site-support.md)
