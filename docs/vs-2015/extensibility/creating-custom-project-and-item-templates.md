---
title: Vytváření vlastních projektů a šablon položek | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b8212b11a60697211f70cd608b6f08a3fade874e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686695"
---
# <a name="creating-custom-project-and-item-templates"></a>Vytváření vlastních šablon projektů a položek
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vytváření vlastních šablon projektů a položek](https://docs.microsoft.com/visualstudio/extensibility/creating-custom-project-and-item-templates).  
  
Visual Studio SDK zahrnuje šablony projektu, které vytvořit vlastní šablonu projektu a šablonu vlastní položky. Tyto šablony zahrnují některých běžných náhrad parametrů a sestavení jako soubory zip. Nejsou nasazeni automaticky a nejsou k dispozici v experimentální instanci aplikace. Souboru zip je nutné zkopírovat soubor do umístění  
  
 Vytvoření šablony šablony umožňují zahrnout šablony do větších rozšíření. To vám umožní implementovat správy verzí na zdrojové soubory a vytvořit skupinu šablony projektů do jednoho balíčku VSIX.  
  
 Pro scénáře vytvoření základní šablony, byste měli použít **exportovat šablonu** průvodce, který uloží do komprimovaného souboru. Další informace o vytvoření základní šablony najdete v tématu [vytváření projektů a šablon položek](../ide/creating-project-and-item-templates.md).  
  
 Spouští se v sadě Visual Studio "15" Preview 4, vyhledávání vlastních projektů a šablon položek už se provede. Rozšíření místo toho musíte zadat soubory manifestu šablon, které popisují umístění instalace služby tyto šablony. Instalace Preview 2 můžete použít k aktualizaci rozšíření VSIX. Pokud provádíte nasazení vašeho rozšíření pomocí MSI, musíte soubory manifestu šablony vygenerovat ručně. Další informace najdete v tématu [upgrade vlastních šablon projektů a položek pro Visual Studio "15"](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-“15”.md). Schéma manifestu šablony je popsána v [Visual Studio Manifest odkaz na schéma šablon](../extensibility/visual-studio-template-manifest-schema-reference.md).  
  
## <a name="creating-a-project-template"></a>Vytvoření šablony projektu  
  
1.  Vytvořte projekt šablony projektu. Můžete najít šablonu projektu v **nový projekt** dialogového okna, v jazyce Visual Basic nebo Visual C# **rozšiřitelnost** složky.  
  
     Tato šablona vygeneruje soubor třídy, ikony, soubor .vstemplate, soubor upravovat projektu s názvem ProjectTemplate.vbproj nebo ProjectTemplate.csproj a některé soubory, které jsou obvykle generovány jinými typy projektů, takový resources.resx soubor, AssemblyInfo soubor a soubor .settings. Každý soubor kódu obsahuje běžné náhrad parametrů, kde je to vhodné.  
  
2.  Přidání a odebrání položek z projektu, jak je vyžadováno pro váš projekt. Neodebírejte soubor upravovat projektu, souboru AssemblyInfo nebo souboru .vstemplate.  
  
3.  Aktualizujte soubor .vstemplate tak, aby odrážela všechny přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) musí obsahovat element [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) – element pro každý soubor mají být zahrnuty v šabloně.  
  
4.  Upravit soubory kódu a další obsah přístupných a přidejte odpovídající parametr nahrazení.  
  
5.  Upravte vygenerovaný obsah podle potřeby.  
  
6.  Sestavte projekt.  
  
     Visual Studio vytvoří soubor .zip, který obsahuje šablonu. Není nasazená, a není k dispozici v experimentální instanci aplikace.  
  
## <a name="creating-an-item-template"></a>Vytvoření šablony položky  
  
1.  Vytvoření šablony položky projektu.  
  
     Tato šablona vygeneruje soubor třídy, ikony, soubor .vstemplate a souboru AssemblyInfo. Soubor třídy obsahuje některé běžné náhrad parametrů.  
  
2.  Přidání a odebrání položek z projektu, jak je vyžadováno pro váš projekt.  
  
3.  Aktualizujte soubor .vstemplate tak, aby odrážela všechny přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) musí obsahovat element [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) – element pro každý soubor mají být zahrnuty v šabloně.  
  
4.  Upravit soubory kódu a další obsah přístupných a přidejte odpovídající parametr nahrazení.  
  
5.  Upravte vygenerovaný obsah podle potřeby.  
  
6.  Sestavte projekt.  
  
     Visual Studio vytvoří komprimovaný soubor, který obsahuje šablonu. Není nasazená, a není k dispozici v experimentální instanci aplikace.  
  
## <a name="deployment"></a>Nasazení  
  
#### <a name="to-deploy-the-project-or-item-template"></a>Pokud chcete nasadit šablonu projektu nebo položky  
  
1.  Vytvořte projekt VSIX. Další informace najdete v tématu [šablonou projektu VSIX](../extensibility/vsix-project-template.md).  
  
2.  Nastavte projekt VSIX jako projekt po spuštění. V **Průzkumníka řešení**, vyberte uzel projektu VSIX, klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.  
  
3.  Nastavte projekt šablony projektu jako prostředek projektu VSIX. Otevřete soubor .vsixmanifest. Přejděte **prostředky** kartě a klikněte na tlačítko **nový**.  
  
    1.  Nastavte **typ** pole **Microsoft.VisualStudio.ProjectTemplate** nebo **Microsoft.VisualStudio.ItemTemplate**.  
  
    2.  Pro zdroj, vyberte **projekt v aktuálním řešení** možnost a potom vyberte projekt, který obsahuje šablonu.  
  
4.  Sestavte řešení a stiskněte klávesu F5. Zobrazí se experimentální instance.  
  
5.  Pro projekt šablony projektu, byste měli vidět vaše šablona projektu uvedené v **nový projekt** dialogového okna (**soubor / nový / Project**), Visual C# nebo Visual Basic uzlu. Pro projekt šablony položky, měli byste vidět položku šablony uvedené v dialogovém okně Přidat novou položku (v **Průzkumníka řešení**, vyberte uzel projektu a klikněte na tlačítko **Add / nová položka**).  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace šablony sady Visual Studio](../ide/visual-studio-template-reference.md)

