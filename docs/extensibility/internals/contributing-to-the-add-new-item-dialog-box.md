---
title: Přispívat na web nové položky dialogové okno Přidat | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 443f52edda5f3bedb2e3f8c8dbbe748254fd7be7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335575"
---
# <a name="contribute-to-the-add-new-item-dialog-box"></a>Přispívání do dialogového okna Přidat novou položku
Podtyp projektu může poskytnout úplné nový adresář položek **přidat novou položku** dialogové okno tak, že zaregistrujete **přidat položku** šablony v části **projekty** podklíč registru.

## <a name="register-add-new-item-templates"></a>Zaregistrujte přidat novou položku – šablony
 V této části se nachází v rámci **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects** v registru. Předpokládejme následující položky registru [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu agregované podle podtyp hypotetické projektu. Položky [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu jsou uvedeny níže.

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

 **AddItemTemplates\TemplateDirs** podklíč obsahuje položky registru pomocí cesty k adresáři, kde k dispozici v položky **přidat novou položku** jsou umístěny dialogové okno.

 Prostředí automaticky načte všechny **AddItemTemplates** dat v rámci **projekty** podklíč registru. Tato data můžou obsahovat data pro základní projekt implementace i data pro konkrétní podtyp typy projektů. Každý podtyp projektu je identifikován podle typu projektu **GUID**. Podtyp projektu můžete určit, že alternativní sadu **přidat položku** šablony by měl být použit pro konkrétní projekt flavored instance podporuje `VSHPROPID_ AddItemTemplatesGuid` výčet z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> v <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> implementace vrátí hodnotu GUID podtyp projektu. Pokud `VSHPROPID_AddItemTemplatesGuid` vlastnost neurčí, základní projekt používá identifikátor GUID.

 Můžete filtrovat položky **přidat novou položku** dialogové okno implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> rozhraní na objekt agregátoru podtyp projektu. Například podtyp projektu, který implementuje databázový projekt na základě agregace [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu, můžete filtrovat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] konkrétní položky ze **přidat novou položku** dialogové okno implementací, filtrování a zapnout, můžete přidat databázové položky specifické pro projekt díky podpoře `VSHPROPID_ AddItemTemplatesGuid` v <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>. Další informace o filtrování a přidávání položek do **přidat novou položku** dialogovém okně naleznete v tématu [přidání položek do dialogových oken přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md).

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>
- [Identifikátory CatID pro objekty, které se obvykle používají k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)