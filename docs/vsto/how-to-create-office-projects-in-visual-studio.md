---
title: 'Postupy: vytváření projektů Office v sadě Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.SelectDocWizard.Page1
- VST.SelectDocWizard.Http
- VST.SelectDocWizard.Extension
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], creating projects
- Office applications [Office development in Visual Studio], creating
- Office projects [Office development in Visual Studio]
- projects [Office development in Visual Studio], creating
- document-level customizations [Office development in Visual Studio], creating
- application-level add-ins [Office development in Visual Studio], creating projects
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 50739bfde7578a49226e5396c8eeb78e56c4b0ae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-office-projects-in-visual-studio"></a>Postupy: Vytváření projektů pro systém Office v prostředí Visual Studio
  Můžete použít [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] vytvoření doplňku VSTO a na úrovni dokumentu vlastní nastavení pro aplikace Microsoft Office. Další informace o těchto typech projektů najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-vsto-add-in-project"></a>Vytvoření projektu doplňku VSTO  
  
1.  Na **soubor** nabídce zvolte **nový**, **projektu**. Pokud integrované vývojové prostředí (IDE) je nastavený na použití [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] nastavení pro vývoj na **soubor** nabídce zvolte **nový**, **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
    > [!NOTE]  
    >  Cíl projektů Office [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] ve výchozím nastavení. Další informace najdete v tématu [profil klienta rozhraní .NET Framework](/dotnet/framework/deployment/client-profile).  
  
2.  V podokně šablon v uzlu pro jazyk, kterou chcete použít, rozbalte položku **Office/SharePoint**.  
  
3.  Vyberte **Office Add in** uzlu.  
  
4.  V seznamu šablon projektu vyberte šablona projektu doplňku VSTO. Seznam dostupných doplňku VSTO šablon projektu, naleznete v části [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md).  
  
    > [!NOTE]  
    >  Pokud nejsou viditelné šablony projektů když vyberete **Office Add in** uzlu, ujistěte se, že **rozhraní .NET Framework 4** nebo novější je vybraný v pole se seznamem v horní části dialogových oken. Šablony projektů Office jsou viditelné pro obě verze rozhraní .NET Framework.  
  
5.  V **název** pole, zadejte název projektu. Ve výchozím nastavení název projektu slouží také jako název řešení.  
  
6.  V **umístění** pole, zadejte cestu, kde chcete vytvořit projekt. Můžete použít absolutní a universal naming convention (UNC) cesty. Nepoužívejte HTTP, FTP nebo jiných protokol cest.  
  
     Umístění mít následujících formátů:  
  
    -   [*jednotky*\]: \  
  
    -   \\\\*Server*\\*sdílené složky*  
  
     Nepoužívejte tyto znaky v umístění:  
  
    -   Znak hvězdičky (*)  
  
    -   Svislé čáry (|)  
  
    -   Dvojtečkou (:) (S výjimkou následujících písmeno jednotky.)  
  
    -   Dvojité uvozovky (") (cesty, které obsahují mezery se nemusí znaky uvozovek).  
  
    -   Menší než (\<)  
  
    -   Větší než (>)  
  
    -   Otazník (?)  
  
    -   Znak procenta (%)  
  
7.  Vyberte **OK** tlačítko.  
  
    > [!NOTE]  
    >  Projekty doplňku ukládají vždy při jejich vytváření. Nemohou být vytvářeny jako dočasné projekty. Další informace o dočasné projekty najdete v tématu [dočasné projekty](http://msdn.microsoft.com/en-us/9cf1944c-7045-44cc-8701-7b0eb4099f2b).  
  
### <a name="to-create-a-document-level-customization-project"></a>Vytvoření projektu přizpůsobení na úrovni dokumentu  
  
1.  Na **soubor** nabídce zvolte **nový**, **projektu**. Pokud vaše IDE je nastavený na použití nastavení vývoj jazyka Visual Basic, na **soubor** nabídce zvolte **nový**, **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
    > [!NOTE]  
    >  Cíl projektů Office [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] ve výchozím nastavení.  Další informace najdete v tématu [profil klienta rozhraní .NET Framework](/dotnet/framework/deployment/client-profile).  
  
2.  V podokně šablon v uzlu pro jazyk, kterou chcete použít, rozbalte položku **Office/SharePoint**.  
  
3.  Vyberte **Office Add in** uzlu.  
  
4.  V seznamu šablon projektu vyberte šablonu projekt na úrovni dokumentu. Seznam šablon k dispozici projekt na úrovni dokumentu najdete v tématu [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md).  
  
    > [!NOTE]  
    >  Pokud nejsou viditelné šablony projektů když vyberete **Office Add in** uzlu, ujistěte se, že **rozhraní .NET Framework 4** nebo novější je vybraný v pole se seznamem v horní části dialogových oken. Šablony projektů Office jsou viditelné pro obě verze rozhraní .NET Framework.  
  
5.  V **název** pole, zadejte název projektu. Ve výchozím nastavení je tento název taky používá pro dokument. Pokud vaše IDE nastaven pro použití Visual C# – vývojové nastavení nebo nastavení obecné vývoj, také zadejte umístění a název řešení.  
  
    > [!NOTE]  
    >  Náhradní znaky nelze použít v cestě umístění projektu nebo název projektu. Navíc pokud plánujete nasadit řešení pro použití v režimu offline, znaky v názvu projektu se musí vejít specifikace protokolu HTTP.  
  
6.  Vyberte **OK** tlačítko.  
  
     **Visual Studio Tools for Office – Průvodce projektem** otevře.  
  
7.  Vyberte **vytvoříte nový textový dokument** Pokud chcete vytvořit nový dokument pro řešení, nebo vyberte **zkopírovat stávající dokument** Pokud chcete přizpůsobit existující dokument.  
  
     Pokud vytvoříte nový textový dokument, zadejte název v **název** pole a vyberte formát dokumentu pomocí **formát** pole. Další informace o dostupných formátů najdete v tématu [architektura z úpravy na úrovni dokumentů](../vsto/architecture-of-document-level-customizations.md).  
  
     Pokud chcete použít stávající dokument, zadejte umístění dokumentu v **úplnou cestu stávající dokument** pole. Můžete použít absolutní cesty a cesty UNC. Nepoužívejte HTTP, FTP nebo jiných protokol cest k dokumentu.  
  
     Umístění mít následujících formátů:  
  
    -   [*jednotky*\]: \  
  
    -   \\\\*Server*\\*sdílené složky*  
  
     Nepoužívejte tyto znaky v umístění:  
  
    -   Znak hvězdičky (*)  
  
    -   Svislé čáry (|)  
  
    -   Dvojtečkou (:) (S výjimkou následujících písmeno jednotky.)  
  
    -   Dvojité uvozovky (") (cesty, které obsahují mezery se nemusí znaky uvozovek).  
  
    -   Menší než (\<)  
  
    -   Větší než (>)  
  
    -   Otazník (?)  
  
    -   Znak procenta (%)  
  
    > [!NOTE]  
    >  Pokud používáte stávající dokument v [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] projektu, používat jenom dokumenty, které byly vytvořeny nebo převést na [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]. Podobně pokud používáte stávající dokument aplikace Word 2010 projektu, používat jenom dokumenty, které byly vytvořeny nebo převést na Wordu 2010. Některé funkce budou zakázané v dokumentu, pokud používáte dokument, který byl vytvořen ve starší verzi aplikace Word. Pokud se pokusíte napsat kód, který používá tyto funkce, které může dojít k chybám ve vašem projektu. Chcete-li převést dokument, otevřete ho v [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] nebo Word 2010 na **soubor** na pásu karet, zvolte **informace o**, **převést**.  
  
8.  Zvolte **Dokončit**.  
  
9. Přidejte projekt složce a jejích podsložkách do seznamu důvěryhodných lokalit v Centru zabezpečení v aplikaci Word v následujících případech:  
  
    -   Vytváříte dokument aplikace Word, který je založen na soubor DOCM a dokument obsahuje projekt VBA nebo hostitelem ovládací prvky Windows Forms. Přidání složky projektu do seznamu důvěryhodných lokalit vám pomůže, ujistěte se, že dokument funguje podle očekávání v době návrhu.  
  
    -   Vytvoříte projekt šablony aplikace Word, který je založen na DOTX souboru. Složce projektu musíte přidat do seznamu důvěryhodných lokalit, aby mohli spustit a ladění projektu.  
  
     Další informace o tom, jak přidat do důvěryhodného umístění dokumentu, najdete v článku na webu společnosti Microsoft Office Online [Create, odebrat nebo změnit důvěryhodném umístění pro soubory](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62).  
  
## <a name="see-also"></a>Viz také  
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)   
 [Spolupráce na vývoji řešení pro systém Office](../vsto/collaborative-development-of-office-solutions.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)  
  
  