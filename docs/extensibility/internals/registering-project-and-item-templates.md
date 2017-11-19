---
title: "Registrace šablon projektů a položek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], adding items
- registry, Add New Item dialog box
- Add New Item dialog box
- Add New Project dialog box
- registry, Add New Project dialog box
ms.assetid: 6b909f93-d7f5-4aec-81c6-ee9ff0f31638
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c1cb9e31384822dddcdd3668bfb3a54bc2782d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="registering-project-and-item-templates"></a>Registrace šablon projektů a položek
Typy projektů musí zaregistrovat adresáře, kde se nachází jejich šablon projektů a položek projektů. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]informace o registraci, které jsou přidružené k vaší typy projektů používá k určení toho, které se zobrazí v **přidat nový projekt** a **přidat novou položku** dialogová okna.  
  
 Další informace o šablonách najdete v tématu [přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
## <a name="registry-entries-for-projects"></a>Položky registru pro projekty  
 Následující příklady ukazují položky registru pod HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<*verze*>. Doprovodné tabulky popisují prvky používané v příkladech.  
  
```  
[Projects\{ProjectGUID}]  
@="MyProjectType"  
"DisplayName"="#2"  
"Package"="{VSPackageGUID}"  
"ProjectTemplatesDir"="C:\\MyProduct\\MyProjectTemplates"  
```  
  
|Název|Typ|Popis|  
|----------|----------|-----------------|  
|@|REG_SZ|Výchozí název projekty druhu.|  
|displayName|REG_SZ|ID prostředku názvu mají být načteny z satelitní knihovny DLL je registrovaná pod balíčky.|  
|Balíček|REG_SZ|ID třídy balíčku je registrovaná pod balíčky.|  
|ProjectTemplatesDir|REG_SZ|Výchozí cesta soubory šablon projektu. Šablona projektu soubory jsou zobrazeny **nový projekt** šablony.|  
  
### <a name="registering-item-templates"></a>Registrace šablon položek  
 Je nutné zaregistrovat adresáři, kde ukládáte šablon položek.  
  
```  
[Projects\{ProjectGUID}\AddItemTemplates\TemplateDirs\{VSPackageGUID}\1]  
@="#7"  
"TemplatesDir"="C:\\MyProduct\\MyProjectItemTemplates "  
"TemplatesLocalizedSubDir"="#10"  
"SortPriority"=dword:00000064  
```  
  
|Název|Typ|Popis|  
|----------|----------|-----------------|  
|@|REG_SZ|ID prostředku pro šablony přidat položku.|  
|TemplatesDir|REG_SZ|Cesta položky projektu zobrazí v dialogovém okně pro **přidat novou položku** průvodce.|  
|TemplatesLocalizedSubDir|REG_SZ|ID prostředku řetězce, který názvy podadresáři TemplatesDir, který obsahuje lokalizované šablony. Protože [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zatížení řetězec prostředku z satelitní knihovny DLL Pokud si je, každý satelitní knihovny DLL může obsahovat různé lokalizované podadresáři název.|  
|SortPriority|REG_DWORD|Nastavit SortPriority, které budou řídit pořadí, ve kterém jsou zobrazeny šablony v **přidat novou položku** dialogové okno. Vyšší hodnoty SortPriority uvedeny dříve v tomto seznamu šablony.|  
  
### <a name="registering-file-filters"></a>Registrace filtry souborů  
 Volitelně můžete zaregistrovat filtry, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] používá, když se zobrazí výzvu pro názvy souborů. Například [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] filtrovat **otevření souboru** dialogové okno je:  
  
 **Soubory Visual C# (\*.cs\*RESX,\*.settings,\*XSD,\*WSDL);\*. cs,\*RESX,\*.settings,\*XSD,\*WSDL)**  
  
 Pro podporu registrace více filtrů, každý filtr je zaregistrován v jeho vlastní podklíčem v HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<*verze*> \Projects\\{ \< *ProjectGUID*>} \Filters\\<*podklíč*>. Název podklíče je libovolný. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ignoruje na podklíč název a používá právě jeho hodnoty.  
  
 Můžete ovládat kontexty, ve kterých se používá filtr nastavením příznaky, které jsou uvedené v následující tabulce. Pokud filtr nemá žádné příznaky nastavit, objeví se po běžné filtry v **přidat existující položku** dialogové okno a **otevření souboru** dialogové okno, ale nebude použito ve **hledání v souborech**  dialogové okno.  
  
```  
[Projects\{ProjectGUID}\Filters\MyLanguageFilter]  
@="#3"  
"CommonOpenFilesFilter"=dword:00000000  
"CommonFindFilesFilter"=dword:00000000  
"FindInFilesFilter"=dword:00000000  
"NotOpenFileFilter"=dword:00000000  
"NotAddExistingItemFilter"=dword:00000000  
"SortPriority"=dword:00000064  
```  
  
|Název|Typ|Popis|  
|----------|----------|-----------------|  
|CommonFindFilesFilter|REG_DWORD|Díky filtr, jeden z běžných filtrů v **hledání v souborech** dialogové okno. Běžné filtry jsou uvedeny v seznamu filtru před filtry, které nejsou označeny jako běžné.|  
|CommonOpenFilesFilter|REG_DWORD|Díky filtr, jeden z běžných filtrů v **otevření souboru** dialogové okno. Běžné filtry jsou uvedeny v seznamu filtru před filtry, které nejsou označeny jako běžné.|  
|FindInFilesFilter|REG_DWORD|Uvádí filtr po běžné filtry v **hledání v souborech** dialogové okno.|  
|NotOpenFileFilter|REG_DWORD|Označuje, že není v použít filtr **otevření souboru** dialogové okno.|  
|NotAddExistingItemFilter|REG_DWORD|Označuje, že není v použít filtr **přidat existující položku** dialogové okno.|  
|SortPriority|REG_DWORD|Nastavit SortPriority, které budou řídit pořadí, ve kterém jsou zobrazeny filtry. Vyšší hodnoty SortPriority uvedeny dříve v tomto seznamu filtru.|  
  
## <a name="directory-structure"></a>Struktura adresářů  
 VSPackages můžete vložit šablonu soubory a složky kdekoli na místním nebo vzdáleném disku, tak dlouho, dokud umístění je registrovaný prostřednictvím metody integrované vývojové prostředí (IDE). Ale pro usnadnění organizace, doporučujeme následující adresářovou strukturu v instalační cestě svůj produkt.  
  
 \Templates  
  
 \Projects (obsahuje šablony projektu)  
  
 \Applications  
  
 \Components  
  
 \ ...  
  
 \ProjectItems (obsahuje položky projektu)  
  
 \Class  
  
 \Form  
  
 \Web stránky  
  
 \HelperFiles (obsahuje soubory používané v položkách projektu více soubory)  
  
 \WizardFiles  
  
## <a name="see-also"></a>Viz také  
 [Přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [Průvodci](../../extensibility/internals/wizards.md)   
 [Lokalizace aplikací](../../ide/localizing-applications.md)   
 [CATIDs pro objekty, které jsou obvykle používány k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)