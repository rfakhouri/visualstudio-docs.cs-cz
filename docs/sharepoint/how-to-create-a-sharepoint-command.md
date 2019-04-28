---
title: 'Postupy: Vytvoření příkazu SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint commands [SharePoint development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d804acd19d585bf9517ce9b8d771290a1f1c214a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435458"
---
# <a name="how-to-create-a-sharepoint-command"></a>Postupy: Vytvoření příkazu SharePoint
  Pokud chcete použít objektový model serveru v rozšíření nástrojů služby SharePoint, je třeba vytvořit vlastní *příkaz serveru SharePoint* pro volání rozhraní API. Příkaz serveru SharePoint definujete v sestavení, které můžete volat přímo do objektového modelu serveru.

 Další informace o účelu příkazů služby SharePoint, naleznete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).

### <a name="to-create-a-sharepoint-command"></a>Vytvoření příkazu SharePoint

1. Vytvořte projekt knihovny tříd, který má následující konfiguraci:

    - Cílí na .NET Framework 3.5. Další informace o výběru cílové architektury, najdete v části [jak: Cílení na určitou verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

    - Cílí AnyCPU nebo x64 platformy. Ve výchozím nastavení cílovou platformu pro projekty knihovny tříd je AnyCPU. Další informace o výběru cílové platformy najdete v tématu [jak: Konfigurace projektů pro cílové platformy](../ide/how-to-configure-projects-to-target-platforms.md).

    > [!NOTE]
    > Příkaz serveru SharePoint nemůže implementovat ve stejném projektu, který definuje rozšíření nástrojů SharePoint, protože příkazů služby SharePoint cílí na rozhraní .NET Framework 3.5 a SharePoint cíl rozšíření nástroje [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Je nutné definovat všechny příkazy služby SharePoint, které jsou používány rozšíření testovacího projektu. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

2. Přidejte odkazy na následující sestavení:

    - Microsoft.VisualStudio.SharePoint.Commands

    - Microsoft.SharePoint

3. Ve třídě v projektu vytvořte metodu, která definuje váš příkaz služby SharePoint. Metoda musí splňovat následující pokyny:

    - Může mít jeden nebo dva parametry.

         První parametr musí být <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> objektu. Tento objekt obsahuje Microsoft.SharePoint.SPSite nebo Microsoft.SharePoint.SPWeb spuštění příkazu. Poskytuje také <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandLogger> objekt, který můžete použít k zápisu zprávy do **výstup** okno nebo **seznam chyb** okna v sadě Visual Studio.

         Druhý parametr může být typ podle vašeho výběru, ale tento parametr je nepovinný. Tento parametr můžete přidat do příkazu SharePoint, pokud potřebujete předat data z rozšíření nástrojů služby SharePoint k příkazu.

    - Může mít návratovou hodnotu, ale tato položka je nepovinná.

    - Druhý parametr a návratová hodnota musí být typ, který lze serializovat pomocí Windows Communication Foundation (WCF). Další informace najdete v tématu [typy podporované serializátorem kontraktu dat](/dotnet/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer) a [horizontálních oddílů pomocí třídy XmlSerializer](/dotnet/framework/wcf/feature-details/using-the-xmlserializer-class).

    - Metoda může mít libovolný viditelnost (**veřejné**, **interní**, nebo **privátní**), a může být statické nebo nestatické.

4. Použít <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute> metody. Tento atribut určuje jedinečný identifikátor pro příkaz; Tento identifikátor nemusí odpovídat názvu metody.

     Při volání příkazu z rozšíření nástrojů služby SharePoint, musíte zadat stejný jedinečný identifikátor. Další informace najdete v tématu [jak: Provedení příkazu SharePoint](../sharepoint/how-to-execute-a-sharepoint-command.md).

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje příkaz SharePoint, který má identifikátor `Contoso.Commands.UpgradeSolution`. Tento příkaz používá rozhraní API v objektovém modelu serveru na upgrade na nasazeném řešení.

 [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#5](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/SharePointCommands/Commands.cs#5)]
 [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#5](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/sharepointcommands/commands.vb#5)]

 Kromě implicitní první <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> parametr, tento příkaz má také parametr vlastní řetězec, který obsahuje úplnou cestu souboru WSP, který se upgraduje na webu služby SharePoint. Tento kód v rámci většího příkladu najdete v tématu [názorný postup: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).

## <a name="compiling-the-code"></a>Kompilování kódu
 Tento příklad vyžaduje odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint.Commands

- Microsoft.SharePoint

## <a name="deploying-the-command"></a>Nasazení příkazu
 Nasazení příkazu, patří příkaz sestavení ve stejném [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] rozšíření (*vsix*) balíček se sestavení rozšíření, které používá příkaz. Také je nutné přidat záznam pro příkaz sestavení v souboru extension.vsixmanifest. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md)
- [Postupy: Provedení příkazu SharePoint](../sharepoint/how-to-execute-a-sharepoint-command.md)
- [Návod: Rozšíření Průzkumníka serveru pro zobrazení částí webu](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)
