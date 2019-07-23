---
title: Vytváření vlastních šablon projektů a položek | Microsoft Docs
ms.date: 3/16/2019
ms.topic: conceptual
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8fbe1a4decebd68b80e6cbe8728c5de84a44c641
ms.sourcegitcommit: 485881e6ba872c7b28a7b17ceaede845e5bea4fe
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2019
ms.locfileid: "68377747"
---
# <a name="create-custom-project-and-item-templates"></a>Vytváření vlastních šablon projektů a položek

Sada Visual Studio SDK obsahuje šablony projektu, které vytvoří vlastní šablonu projektu a šablonu vlastní položky. Tyto šablony zahrnují některých běžných náhrad parametrů a sestavení jako soubory zip. Nejsou nasazeni automaticky a nejsou k dispozici v experimentální instanci aplikace. Vygenerovaný soubor ZIP je nutné zkopírovat do adresáře šablon uživatele.

Vytvoření šablony šablony umožňují zahrnout šablony do větších rozšíření. To umožňuje implementovat řízení verze ve zdrojových souborech a vytvořit skupinu projektů šablon do jednoho balíčku VSIX.

Můžete také nakonfigurovat šablonu pro instalaci balíčků NuGet. Další informace najdete v tématu [balíčky NuGet v šablonách sady Visual Studio](/nuget/visual-studio-extensibility/visual-studio-templates).

Pro scénáře vytvoření základní šablony, byste měli použít **exportovat šablonu** průvodce, který uloží do komprimovaného souboru. Další informace o vytváření základních šablon naleznete v tématu [vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md).

> [!NOTE]
> Spouští se v sadě Visual Studio 2017, vyhledávání vlastních projektů a šablon položek už se provede. Rozšíření místo toho musíte zadat soubory manifestu šablon, které popisují umístění instalace služby tyto šablony. Visual Studio 2017 můžete použít k aktualizaci rozšíření VSIX. Pokud provádíte nasazení vašeho rozšíření pomocí MSI, musíte soubory manifestu šablony vygenerovat ručně. Další informace naleznete v tématu [Upgrade vlastních šablon projektů a položek pro Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Schéma manifestu šablony je dokumentováno v [referenčních informacích o schématu manifestu šablony sady Visual Studio](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="create-a-project-template"></a>Vytvoření šablony projektu

1. Vytvořte projekt šablony projektu. Šablonu projektu najdete v dialogovém okně **Nový projekt** , a to tak, že vyhledáte "šablona projektu" a vyberete C# buď verzi Visual Basic.

     Šablona vygeneruje soubor třídy, ikonu, soubor *. vstemplate* , upravitelný soubor projektu s názvem *ProjectTemplate. vbproj* nebo *ProjectTemplate. csproj*a některé soubory, které jsou obvykle generovány jinými typy projektů, například  *Resources. resx* soubor, soubor *AssemblyInfo* a soubor *. Settings* . Každý soubor kódu obsahuje běžné náhrad parametrů, kde je to vhodné.

![výběr projektu šablony projektu](media/project-template-selection.png)


2. Přidání a odebrání položek z projektu, jak je vyžadováno pro váš projekt. Neodstraňujte upravitelný soubor projektu, soubor *AssemblyInfo* nebo soubor *. vstemplate* .

3. Aktualizujte soubor *. vstemplate* tak, aby odrážel všechna přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) musí obsahovat element [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) – element pro každý soubor mají být zahrnuty v šabloně.

4. Upravit soubory kódu a další obsah přístupných a přidejte odpovídající parametr nahrazení.

5. Upravte vygenerovaný obsah podle potřeby.

6. Sestavte projekt.

     Visual Studio vytvoří soubor *. zip* , který obsahuje vaši šablonu. Není nasazená, a není k dispozici v experimentální instanci aplikace.

## <a name="create-an-item-template"></a>Vytvoření šablony položky

1. Vytvoření šablony položky projektu.

     Šablona vygeneruje soubor třídy, ikonu, soubor *. vstemplate* a soubor *AssemblyInfo* . Soubor třídy obsahuje některé běžné náhrad parametrů.

2. Přidání a odebrání položek z projektu, jak je vyžadováno pro váš projekt.

3. Aktualizujte soubor *. vstemplate* tak, aby odrážel všechna přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) musí obsahovat element [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) – element pro každý soubor mají být zahrnuty v šabloně.

4. Upravit soubory kódu a další obsah přístupných a přidejte odpovídající parametr nahrazení.

5. Upravte vygenerovaný obsah podle potřeby.

6. Sestavte projekt.

     Visual Studio vytvoří komprimovaný soubor, který obsahuje šablonu. Není nasazená, a není k dispozici v experimentální instanci aplikace.

## <a name="deployment"></a>Nasazení

### <a name="to-deploy-the-project-or-item-template"></a>Nasazení šablony projektu nebo položky

1. Vytvořte projekt VSIX. Další informace naleznete v tématu [Šablona projektu VSIX](../extensibility/vsix-project-template.md).

2. Nastavte projekt VSIX jako projekt po spuštění. V **Průzkumníka řešení**, vyberte uzel projektu VSIX, klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.

3. Nastavte projekt šablony projektu jako prostředek projektu VSIX. Otevřete soubor *. vsixmanifest* . Přejděte **prostředky** kartě a klikněte na tlačítko **nový**.

    1. Nastavte **typ** pole **Microsoft.VisualStudio.ProjectTemplate** nebo **Microsoft.VisualStudio.ItemTemplate**.

    2. Pro zdroj, vyberte **projekt v aktuálním řešení** možnost a potom vyberte projekt, který obsahuje šablonu.

4. Sestavte řešení a stiskněte klávesu **F5**. Zobrazí se experimentální instance.

5. V projektu šablony projektu by se měla zobrazit šablona projektu uvedená v dialogovém okně **Nový projekt** (**soubor** > **Nový** > **projekt**) v uzlu vizuál C# nebo Visual Basic. Pro projekt šablony položky by se měla zobrazit Šablona položky uvedená v dialogovém okně **Přidat novou položku** . Chcete-li zobrazit dialogové okno **Přidat novou položku** , vyberte z **Průzkumník řešení**uzel projektu a klikněte na tlačítko **Přidat** > **novou položku**).

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace šablony sady Visual Studio](../ide/creating-project-and-item-templates.md)
- [Balíčky NuGet ve šablony sady Visual Studio](/nuget/visual-studio-extensibility/visual-studio-templates)
