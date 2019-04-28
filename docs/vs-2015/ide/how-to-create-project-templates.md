---
title: 'Postupy: Vytváření šablon projektu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- Visual Studio templates, creating project templates
- project templates, metadata files
- Visual Studio templates, project templates
- project templates, custom template locations
- project templates, creating
ms.assetid: a1a6999d-a34c-48a8-b1cf-027eb5c76398
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5a43fe714028b7211904a0bb993d2964bfe612ce
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63416923"
---
# <a name="how-to-create-project-templates"></a>Postupy: Vytváření šablon projektu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento postup umožňuje vytvořit pomocí šablony **exportovat šablonu** průvodce, který zabalí vaše šablony v souboru .zip. Můžete také vytvořit šablony ve formátu souboru VSIX pro vylepšené nasazení s použitím Průvodce exportem šablony rozšíření nebo pomocí šablon, které jsou součástí [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)], nebo můžete vytvořit šablony ručně.  
  
### <a name="to-create-a-custom-project-template-with-the-standard-export-template-wizard"></a>Chcete-li vytvořit vlastní šablonu projektu pomocí standardního Průvodce exportovat šablonu  
  
1. Vytvoření projektu.  
  
    > [!NOTE]
    > Při pojmenování projektu, který bude sloužit jako zdroj šablony, používejte pouze znaky platný identifikátor. Šablonu exportovat z projektu s názvem se neplatné znaky. mohou způsobit chyby kompilace v budoucnu projekty založené na šabloně. Další informace o platný identifikátor znaků naleznete v tématu [deklarované názvy elementů](http://msdn.microsoft.com/library/09d8843b-c0dc-4afe-9dab-87c439a69e66).  
  
2. Upravte projekt, dokud nebude připravený exportovat jako šablonu.  
  
3. Podle potřeby upravte soubory kódu k označení, kde by měla probíhat náhrada parametru. Další informace o nahrazení parametru najdete v tématu [jak: Nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).  
  
4. Na **souboru** nabídky, klikněte na tlačítko **exportovat šablonu**. **Exportovat šablonu** otevře se průvodce.  
  
5. Klikněte na tlačítko **projektu šablony**.  
  
6. Pokud máte více než jeden projekt v aktuálním řešení, vyberte projekty, které chcete exportovat do šablony.  
  
7. Klikněte na **Další**.  
  
8. Vyberte ikonu a image ve verzi preview pro šablonu. Zobrazí **nový projekt** dialogové okno.  
  
9. Zadejte název šablony a popis.  
  
10. Klikněte na tlačítko **Dokončit**. Váš projekt je exportovali do souboru ZIP a umístí do zadané výstupní umístění a k importu do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
     Pokud máte [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] nainstalované, můžete zabalit dokončená šablona v souboru VSIX pro nasazení s použitím **projekt VSIX** šablony. Další informace najdete v tématu [Začínáme s šablonou projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Postupy: Vytváření šablon položek](../ide/how-to-create-item-templates.md)
