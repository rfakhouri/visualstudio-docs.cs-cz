---
title: "Které přispívají k informacím nové položky dialogové okno Přidat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 923d95256a3ab0e63bdcf35c7ae38d70a117fa02
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="contributing-to-the-add-new-item-dialog-box"></a>Které přispívají k informacím přidat novou položku – dialogové okno
Podtyp projektu může poskytnout úplný nový adresář položek pro **přidat novou položku** dialogové okno tak, že zaregistrujete **přidat položku** šablony v části `Projects` podklíč registru.  
  
## <a name="registering-add-new-item-templates"></a>Registrace pro přidání nové položky šablony  
 V této části se nachází v **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects** v registru. Níže uvedené položky registru předpokládá [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu agregaci podtypem hypotetický projektu. Položky pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu jsou uvedeny níže.  
  
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
  
 `AddItemTemplates\TemplateDirs` Podklíč obsahuje položky registru s cestou k adresáři, kde k dispozici v položky **přidat novou položku** jsou umístěny dialogové okno.  
  
 Prostředí automaticky načte všechny `AddItemTemplates` data v rámci `Projects` podklíč registru. To může zahrnovat data pro implementace základní projekt, a také data pro konkrétní dílčí typy projektů. Každý projekt dílčí je určený podle typu projektu `GUID`. Dílčí projektu můžete určit, že alternativní sada `Add Item` šablony má být používána pro konkrétní projekt podporu instanci podpora `VSHPROPID_ AddItemTemplatesGuid` výčtu z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> v <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> implementace vrátit identifikátor GUID Hodnota dílčí projektu. Pokud `VSHPROPID_AddItemTemplatesGuid` vlastnost neurčí, základní projekt se používá identifikátor GUID.  
  
 Můžete filtrovat položky v **přidat novou položku** dialogové okno implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> rozhraní na objekt projektu dílčí agregátoru. Například na podtyp projektu, který implementuje databázového projektu agregací [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu, můžete filtrovat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] konkrétní položky z **přidat novou položku** dialogové okno implementací filtrování a v zapnout, můžete přidat Díky podpoře databáze konkrétní položky projektu `VSHPROPID_ AddItemTemplatesGuid` v <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>. Další informace o filtrování a přidávání položek do **přidat novou položku** dialogové okno, najdete v části [přidávání položek přidat novou položku dialogových oknech](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Identifikátory CATID pro objekty používané obvykle k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)