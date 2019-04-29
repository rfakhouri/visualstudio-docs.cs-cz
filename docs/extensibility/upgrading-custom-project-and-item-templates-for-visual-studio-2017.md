---
title: Upgrade vlastních šablon projektů a položek pro Visual Studio 2017 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ad02477b-e101-4f32-aeb7-292bf95d5c2f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: cb4defa206d176e57804e6d2473262568cd5edbf
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434205"
---
# <a name="upgrade-custom-project-and-item-templates-for-visual-studio-2017"></a>Upgrade vlastních šablon projektů a položek pro Visual Studio 2017

Spouští se v sadě Visual Studio 2017, Visual Studio zjistí šablony projektů a položek, které byly nainstalovány VSIX nebo byl soubor MSI jiným způsobem k předchozím verzím sady Visual Studio. Pokud používáte rozšíření, které používají vlastní projekt nebo šablony položek, musíte aktualizovat vaše rozšíření. Tento článek vysvětluje, co musíte udělat.

Tato změna ovlivní pouze aplikace Visual Studio 2017. To nemá vliv na předchozích verzích sady Visual Studio.

Pokud chcete vytvořit šablonu projektu nebo položky jako součást rozšíření VSIX, přečtěte si téma [vytváření vlastních šablon projektů a položek](../extensibility/creating-custom-project-and-item-templates.md).

## <a name="template-scanning"></a>Kontrola šablon

V předchozích verzích sady Visual Studio **devenv/Setup** nebo **devenv/installvstemplates** zkontrolovaných místním disku do šablon projektů a položek. Spouští se v sadě Visual Studio 2017, kontrola se provádí pouze pro umístění úrovni uživatele. Výchozí umístění individuální **%USERPROFILE%\Documents\\< verze sady Visual Studio\>\Templates\\**. Toto umístění se používá pro šablony, které jsou generované **projektu** > **Export šablony...**  příkazu, pokud **automaticky importovat šablonu do sady Visual Studio** je vybraná možnost v průvodci.

Na jiných místech (od uživatele) musí obsahovat manifest(.vstman) soubor, který určuje umístění a další vlastnosti šablony. Souboru .vstman generováno spolu se souborem .vstemplate, používá se pro šablony. Pokud nainstalujete rozšíření pomocí VSIX, můžete to provést opětovnou kompilací rozšíření v sadě Visual Studio 2017. Ale pokud používáte byl soubor MSI, budete muset provést změny ručně. Seznam co je potřeba udělat, aby tyto změny najdete v tématu **upgrady pro rozšíření nainstalované pomocí. MSI** později na této stránce.

## <a name="how-to-update-a-vsix-extension-with-project-or-item-templates"></a>Postup aktualizace rozšíření VSIX projekt nebo šablony položek

1. Otevřete řešení v sadě Visual Studio 2017. Zobrazí se výzva k upgradu kód. Klikněte na **OK**.

2. Po dokončení upgradu, budete muset změnit verzi cíle instalace. V projektu VSIX, otevřete soubor source.extension.vsixmanifest a vyberte **cíle instalace** kartu. Pokud **rozsah verzí** pole je **[14.0]**, klikněte na tlačítko **upravit** a změnit tak, aby obsahovala Visual Studio 2017. Například můžete nastavit **[14.0,15.0]** nainstalovat rozšíření pro Visual Studio 2015 nebo Visual Studio 2017 nebo do **[15.0]** k její instalaci pouze Visual Studio 2017.

3. Znovu zkompilujte kód.

4. Zavřete Visual Studio.

5. Nainstalujte VSIX.

6. Otestovat aktualizaci následujícím způsobem:

    1. Skenování změnu souboru se aktivuje pomocí následujícího klíče registru:

         **Přidat reg hklm\software\microsoft\visualstudio\15.0\VSTemplate /v DisableTemplateScanning /t REG_DWORD /d 1 /reg:32**

    2. Po přidání klíče spustit **devenv/installvstemplates**.

    3. Znovu otevřete Visual Studio. Měli byste najít vaše šablony v očekávaném umístění.

    > [!NOTE]
    > Šablony projektů Visual Studio Extensibility nejsou k dispozici, když existuje klíč registru. Je nutné odstranit klíč registru (a znovu spusťte **devenv/installvstemplates**) k jejich použití.

## <a name="other-recommendations-for-deploying-project-and-item-templates"></a>Další doporučení pro nasazení šablony projektů a položek

- Vyhněte se použití soubory ZIP šablony. Metoda ZIP šablony, které soubory musí mít nekomprimované získat prostředků a obsahu, tak budou costlier používat. Místo toho byste měli nasadit šablony projektů a položek jako samostatné soubory podle jejich vlastní adresáře pro urychlení inicializace šablony. Pro rozšíření VSIX budou úlohy sestavení sady SDK automaticky rozbalte všechny ZIP šablony při vytváření souboru VSIX.

- Vyhněte se použití balíčku/resource ID položky pro šablonu název, popis, ikona nebo ve verzi preview, aby se zabránilo načítání sestavení zbytečné prostředků při zjišťování šablon. Lokalizované manifesty místo, můžete použít k vytvoření šablony položky pro každé národní prostředí, která používá lokalizované názvy nebo vlastnosti.

- Chcete-li zahrnout šablony jako souboru položky, generování manifestu nemusí poskytnout očekávané výsledky. V takovém případě budete muset přidat ručně vygenerovaný manifest do projektu VSIX.

## <a name="file-changes-in-project-and-item-templates"></a>Změny souborů šablon projektů a položek
Jsme zobrazí body rozdíl mezi Visual Studio 2015 a Visual Studio 2017 verze souborů šablon, takže můžete vytvořit nové soubory správně.

 Tady je výchozí soubor .vstemplate projekt vytvořen pomocí sady Visual Studio 2015:

```xml
<?xml version="1.0" encoding="utf-8"?>
<VSTemplate Version="3.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">
  <TemplateData>
    <Name>ProjectTemplate1</Name>
    <Description>ProjectTemplate1</Description>
    <Icon>ProjectTemplate1.ico</Icon>
    <ProjectType>CSharp</ProjectType>
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>
    <SortOrder>1000</SortOrder>
    <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>
    <CreateNewFolder>true</CreateNewFolder>
    <DefaultName>ProjectTemplate1</DefaultName>
    <ProvideDefaultName>true</ProvideDefaultName>
  </TemplateData>
  <TemplateContent>
    <Project File="ProjectTemplate.csproj" ReplaceParameters="true">
      <ProjectItem ReplaceParameters="true" TargetFileName="Properties\AssemblyInfo.cs">AssemblyInfo.cs</ProjectItem>
      <ProjectItem ReplaceParameters="true" OpenInEditor="true">Class1.cs</ProjectItem>
    </Project>
  </TemplateContent>
</VSTemplate>

```

 Tady je souboru .vstman (najdete ho v adresáři projektu VSIX manifestu), který je výsledkem znovu sestavit projekt VSIX:

```xml
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">
  <VSTemplateContainer TemplateType="Project">
    <RelativePathOnDisk>CSharp\1033\ProjectTemplate1</RelativePathOnDisk>
    <TemplateFileName>ProjectTemplate1.vstemplate</TemplateFileName>
    <VSTemplateHeader>
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
        <Name>ProjectTemplate1</Name>
        <Description>ProjectTemplate1</Description>
        <Icon>ProjectTemplate1.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>
        <SortOrder>1000</SortOrder>
        <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>
        <CreateNewFolder>true</CreateNewFolder>
        <DefaultName>ProjectTemplate1</DefaultName>
        <ProvideDefaultName>true</ProvideDefaultName>
      </TemplateData>
    </VSTemplateHeader>
  </VSTemplateContainer>
</VSTemplateManifest>

```

 Na základě informací poskytnutých [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) element zůstává stejná.  **\<VSTemplateContainer >** element odkazuje na soubor .vstemplate pro přidruženou šablonu.

 Tady je výchozí soubor .vstemplate položky vytvořené pomocí sady Visual Studio 2015:

```xml
<?xml version="1.0" encoding="utf-8"?>
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">
  <TemplateData>
    <Name>ItemTemplate1</Name>
    <Description>ItemTemplate1</Description>
    <Icon>ItemTemplate1.ico</Icon>
    <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>
    <ProjectType>CSharp</ProjectType>
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>
    <DefaultName>Class.cs</DefaultName>
  </TemplateData>
  <TemplateContent>
    <References>
      <Reference>
        <Assembly>System</Assembly>
      </Reference>
    </References>
    <ProjectItem ReplaceParameters="true">Class.cs</ProjectItem>
  </TemplateContent>
</VSTemplate>

```

 Tady je souboru .vstman (najdete ho v adresáři projektu VSIX manifestu), který je výsledkem znovu sestavit projekt VSIX:

```xml
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">
  <VSTemplateContainer TemplateType="Item">
    <RelativePathOnDisk>CSharp\1033\ItemTemplate1</RelativePathOnDisk>
    <TemplateFileName>ItemTemplate1.vstemplate</TemplateFileName>
    <VSTemplateHeader>
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
        <Name>ItemTemplate1</Name>
        <Description>ItemTemplate1</Description>
        <Icon>ItemTemplate1.ico</Icon>
        <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>
        <ProjectType>CSharp</ProjectType>
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>
        <DefaultName>Class.cs</DefaultName>
      </TemplateData>
    </VSTemplateHeader>
  </VSTemplateContainer>
</VSTemplateManifest>
```

 Na základě informací poskytnutých  **\<TemplateData >** element zůstává stejná.  **\<VSTemplateContainer >** element odkazuje na soubor .vstemplate pro přidruženou šablonu

 Další informace o různých prvků souboru .vstman najdete v tématu [Visual Studio Manifest odkaz na schéma šablon](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="upgrades-for-extensions-installed-with-an-msi"></a>Upgrady pro rozšíření nainstalované pomocí. INSTALAČNÍ SLUŽBY MSI

Některá rozšíření využívajícím MSI nasazení šablony do společného umístění šablon například následující adresáře:

- **\<Visual Studio Instalační adresář > \Common7\IDE\\< ProjectTemplates/šablon položek >**

- **\<Visual Studio Instalační adresář > \Common7\IDE\Extensions\\< ExtensionName\>\\< projektů a šablon položek >**

Pokud vaše rozšíření provede nasazení služby na základě Instalační služby MSI, musíte do manifestu šablony vygenerovat ručně a ujistěte se, že je součástí instalace rozšíření. Porovnání výše uvedených příkladech .vstman a [Visual Studio Manifest odkaz na schéma šablon](../extensibility/visual-studio-template-manifest-schema-reference.md).

Vytvořit samostatný manifesty pro šablony projektů a položek a by měl ukazují na kořenový adresář šablon jak je uvedeno výše. Vytvořte jeden manifest rozšíření a národní prostředí.

## <a name="see-also"></a>Viz také:

- [Řešení potíží se zjišťováním šablon](troubleshooting-template-discovery.md)
- [Vytváření vlastních šablon projektů a položek](creating-custom-project-and-item-templates.md)