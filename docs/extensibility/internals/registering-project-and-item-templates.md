---
title: Registrace šablon projektů a položek | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], adding items
- registry, Add New Item dialog box
- Add New Item dialog box
- Add New Project dialog box
- registry, Add New Project dialog box
ms.assetid: 6b909f93-d7f5-4aec-81c6-ee9ff0f31638
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 84beaf97bda8d94872be22c6f5d247a746d1ecd3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66319502"
---
# <a name="registering-project-and-item-templates"></a>Registrace šablon projektů a položek
Typy projektů musíte zaregistrovat adresáře, kde se nachází jejich šablony projektů a položek projektů. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] informace o registraci přidružený k vaší typy projektů používá k určení, co se má zobrazit v **přidat nový projekt** a **přidat novou položku** dialogových oknech.

 Další informace o šablonách najdete v tématu [přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md).

## <a name="registry-entries-for-projects"></a>Položky registru pro projekty
 Následující příklady ukazují položky registru v rámci HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<*verze*>. Související tabulky popisují prvky použité v případech.

```
[Projects\{ProjectGUID}]
@="MyProjectType"
"DisplayName"="#2"
"Package"="{VSPackageGUID}"
"ProjectTemplatesDir"="C:\\MyProduct\\MyProjectTemplates"
```

|Name|Typ|Popis|
|----------|----------|-----------------|
|@|REG_SZ|Výchozí název projektů tohoto druhu.|
|displayName|REG_SZ|ID prostředku, který se má načíst z satelitní knihovny DLL název zaregistrován balíčky.|
|Balíček|REG_SZ|ID třídy balíčku zaregistrován balíčky.|
|ProjectTemplatesDir|REG_SZ|Výchozí cesty k souboru šablony projektu. Soubory šablon projektu se zobrazí podle **nový projekt** šablony.|

### <a name="registering-item-templates"></a>Registrace šablon položek
 Je nutné zaregistrovat na adresář, kam ukládat šablony položek.

```
[Projects\{ProjectGUID}\AddItemTemplates\TemplateDirs\{VSPackageGUID}\1]
@="#7"
"TemplatesDir"="C:\\MyProduct\\MyProjectItemTemplates "
"TemplatesLocalizedSubDir"="#10"
"SortPriority"=dword:00000064
```

| Name | Typ | Popis |
|--------------------------|-----------| - |
| @ | REG_SZ | ID prostředku pro přidat položku šablony. |
| TemplatesDir | REG_SZ | Cesta položky projektu zobrazí v dialogovém okně **přidat novou položku** průvodce. |
| TemplatesLocalizedSubDir | REG_SZ | ID prostředku řetězce, který podadresáři TemplatesDir názvů, který obsahuje lokalizované šablony. Protože [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zatížení prostředek řetězce ze satelitní knihovny DLL Pokud je máte, každý satelitní knihovny DLL může obsahovat název jiné lokalizované podadresáře. |
| SortPriority | REG_DWORD | Nastavte SortPriority k řízení pořadí, ve kterém šablony se zobrazují v **přidat novou položku** dialogové okno. Vyšší hodnoty SortPriority zobrazí výše v seznamu šablon. |

### <a name="registering-file-filters"></a>Registrace filtry souborů
 Volitelně můžete zaregistrovat filtry, které [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] používá, když ho vyzve k zadání názvů souborů. Například [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] filtrovat **otevřít soubor** dialogové okno je:

 **Visual C# Files (\*.cs,\*.resx,\*.settings,\*.xsd,\*.wsdl);\*.cs,\*.resx,\*.settings,\*.xsd,\*.wsdl)**

 Pro podporu registrace více filtrů, každý filtr je zaregistrován ve vlastní podklíč pod HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<*verze*> \Projects\\{ \< *ProjectGUID*>} \Filters\\<*podklíč*>. Název podklíče je libovolný. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ignoruje v podklíči název a používá jenom jeho hodnoty.

 Můžete řídit kontextech, ve kterých se používá filtr tak, že nastavíte příznaky, které jsou uvedeny v následující tabulce. Pokud filtr nemá nastaveny žádné příznaky, objeví se po běžné filtry v **přidat existující položku** dialogové okno a **otevřít soubor** dialogovému oknu, ale nesmí být použity v **najít v souborech**  dialogové okno.

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

|Name|Typ|Popis|
|----------|----------|-----------------|
|CommonFindFilesFilter|REG_DWORD|Vytvoří jeden z běžných filtrů filtr na **najít v souborech** dialogové okno. Běžné filtry jsou uvedeny v seznamu filtru před filtry, které nejsou označeny jako běžné.|
|CommonOpenFilesFilter|REG_DWORD|Vytvoří jeden z běžných filtrů filtr na **otevřít soubor** dialogové okno. Běžné filtry jsou uvedeny v seznamu filtru před filtry, které nejsou označeny jako běžné.|
|FindInFilesFilter|REG_DWORD|Seznam filtru po běžné filtry v **najít v souborech** dialogové okno.|
|NotOpenFileFilter|REG_DWORD|Označuje, že se nepoužívá filtr **otevřít soubor** dialogové okno.|
|NotAddExistingItemFilter|REG_DWORD|Označuje, že se nepoužívá filtr **přidat existující položku** dialogové okno.|
|SortPriority|REG_DWORD|Nastavit SortPriority k řízení pořadí, ve kterém jsou zobrazeny filtry. Vyšší hodnoty SortPriority zobrazí výše v seznamu filtrů.|

## <a name="directory-structure"></a>Adresářová struktura
 Rozšíření VSPackages můžete do šablony soubory a složky, kdekoli na místním nebo vzdáleném disk, tak dlouho, dokud umístění je zaregistrované prostřednictvím integrovaného vývojového prostředí (IDE). Ale pro usnadnění organizace, doporučujeme následující adresářovou strukturu v cestě instalace produktu.

 \Templates

 \Projects (obsahuje šablony projektu)

 \Applications

 \Components

 \ ...

 \ProjectItems (obsahuje položky projektu)

 \Class

 \Form

 \Web Page

 \HelperFiles (obsahuje soubory používané v položkách projektu více soubory)

 \WizardFiles

## <a name="see-also"></a>Viz také

- [Přidávání šablon projektů a položek projektů](../../extensibility/internals/adding-project-and-project-item-templates.md)
- [Průvodci](../../extensibility/internals/wizards.md)
- [Lokalizace aplikací](../../ide/globalizing-and-localizing-applications.md)
- [Identifikátory CATID pro objekty používané obvykle k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)