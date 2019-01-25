---
title: Přispívat na web nové položky dialogové okno Přidat | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d288f2d007fd0f923021847179326069959d3698
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54762372"
---
# <a name="contributing-to-the-add-new-item-dialog-box"></a>Přispívání do dialogového okna Přidat novou položku
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Podtyp projektu může poskytnout úplné nový adresář položek **přidat novou položku** dialogové okno tak, že zaregistrujete **přidat položku** šablony v části `Projects` podklíč registru.  
  
## <a name="registering-add-new-item-templates"></a>Registrace šablon přidat novou položku  
 V této části se nachází v rámci **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects** v registru. Předpokládejme následující položky registru [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] projektu agregované podle podtyp hypotetické projektu. Položky [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] projektu jsou uvedeny níže.  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}]  
@="#2143"  
"DefaultProjectExtension"="vbproj"  
"PossibleProjectExtensions"="vbproj;vbp"  
"ProjectTemplatesDir"="visualStudioInstallPath\\Vb\\.\\VBProjects"  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}\AddItemTemplates\TemplateDirs\{12345678-1234-1234-1122334455667788}\/1]  
@="#100"  
"TemplatesDir"="projectSubTypeTemplatesDir\\VBProjectItems"  
```  
  
 `AddItemTemplates\TemplateDirs` Podklíč obsahuje položky registru pomocí cesty k adresáři, kde k dispozici v položky **přidat novou položku** jsou umístěny dialogové okno.  
  
 Prostředí automaticky načte všechny `AddItemTemplates` dat v rámci `Projects` podklíč registru. To může zahrnovat data pro základní projekt implementace i data pro konkrétní podtyp typy projektů. Každý podtyp projektu je identifikován podle typu projektu `GUID`. Podtyp projektu můžete určit, že alternativní sadu `Add Item` šablony by měl být použit pro konkrétní projekt flavored instance podporuje `VSHPROPID_ AddItemTemplatesGuid` výčet z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> v <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> implementace vrátí identifikátor GUID Hodnota podtyp projektu. Pokud `VSHPROPID_AddItemTemplatesGuid` vlastnost neurčí, základní projekt používá identifikátor GUID.  
  
 Můžete filtrovat položky **přidat novou položku** dialogové okno implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> rozhraní na objekt agregátoru podtyp projektu. Například podtyp projektu, který implementuje databázový projekt na základě agregace [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] projektu, můžete filtrovat [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] konkrétní položky ze **přidat novou položku** dialogové okno implementací, filtrování a zapnout, můžete přidat Díky podpoře databáze konkrétní položky projektu `VSHPROPID_ AddItemTemplatesGuid` v <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>. Další informace o filtrování a přidávání položek do **přidat novou položku** dialogovém okně naleznete v tématu [přidání položky, které chcete přidat novou položku dialogových oknech](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Identifikátory CATID pro objekty používané obvykle k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)
