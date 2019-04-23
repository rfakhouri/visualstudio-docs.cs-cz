---
title: Rozšíření balení a nasazení SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4bb98e2b1c83ff06570a77dc84ce6a7bf690f81d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60096995"
---
# <a name="extend-sharepoint-packaging-and-deployment"></a>Rozšíření balení a nasazení SharePoint
  Balení a nasazení procesu pro projekty SharePoint můžete rozšířit.

## <a name="create-deployment-steps"></a>Vytvořit postup nasazení
 Při nasazení projektu služby SharePoint, [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] provede série kroků nasazení. Visual Studio obsahuje vestavěné kroky nasazení pro mnoho úloh, jako je například stahování a přidávají řešení. Můžete ale také vytvořit vlastní kroky nasazení.

 Názorný postup ukazuje, jak vytvořit krok nasazení, najdete v části [názorný postup: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).

## <a name="create-deployment-configurations"></a>Vytvoření konfigurace nasazení
 Konfigurace nasazení je sada kroky nasazení, který je proveden pro daný projekt, ale může mít vliv na všechny položky Sharepointového projektu. Každé nasazení konfigurace zahrnuje jednu sadu kroků, které se spustí v případě, že projekt je nasazen a jinou sadu, která se spustí, až projekt odvolán. [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] obsahuje dva předdefinované konfigurace nasazení, ale můžete také vytvořit svoje vlastní. Při vytváření konfigurace nasazení, můžete použít vestavěné kroky nasazení a kroky nasazení, které vytvoříte.

 Návod, jak vytvořit konfiguraci nasazení najdete v tématu [názorný postup: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).

## <a name="run-code-when-a-sharepoint-solution-is-deployed-or-retracted"></a>Spuštění kódu pokud je řešení služby SharePoint nasazen nebo stažen
 Můžete zpracovávat události provádět další úkoly při řešení služby SharePoint nasazen nebo stažen. Visual Studio vyvolává události, které dokáže zpracovat v následujících scénářích:

- Před a po každém nasazení provádí se krok pro položku Sharepointového projektu. Další informace najdete v tématu [jak: Spuštění kódu při provádění kroků nasazení](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md).

- Před a po je projekt SharePoint nasazen nebo stažen. Další informace najdete v tématu [jak: Spuštění kódu pokud je projekt SharePoint nasazen nebo stažen](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md).

## <a name="handle-deployment-conflicts"></a>Zpracování konfliktů nasazení
 Některé typy položek projektu služby SharePoint, včetně modulů, webové části, seznam instancí a typy obsahu, poskytují nasazení integrovaných řešení konfliktů. Při nasazení řešení, které obsahuje jeden z těchto položek projektu sady Visual Studio nejprve zkontroluje, zda soubor již existuje na webu služby SharePoint se stejným názvem, adresa URL nebo ID jako soubor v položce, kterou nasazujete. Pokud došlo ke konfliktu, Visual Studio může automaticky vyřešit konflikt nebo můžete vyzvat, můžete určit, jestli chcete mít Visual Studio konflikt vyřešit nebo zrušení nasazení. Další informace najdete v tématu [řešení potíží s balení a nasazení SharePoint](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).

 Poskytnutím vlastní kód, který kontroluje a řeší konflikty při nasazení můžete rozšířit tuto funkci. Další informace najdete v tématu [jak: Zpracování konfliktů nasazení](../sharepoint/how-to-handle-deployment-conflicts.md).

## <a name="run-command-line-operations-before-or-after-a-project-is-deployed"></a>Operace příkazového řádku spustit před nebo po nasazení projektu
 Pokud chcete spustit operaci příkazový řádek po nasazení řešení služby SharePoint, můžete nastavit <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PreDeploymentCommand%2A> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PostDeploymentCommand%2A> vlastnosti <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu. Visual Studio provede příkazy před a po nasazení projektu.

 V některých případech se může zobrazit konflikty při nasazení. Řešení konfliktů několika různými způsoby. Další informace najdete v tématu [balení a nasazení řešení SharePoint](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).

## <a name="customize-validation-rules"></a>Přizpůsobení pravidel ověřování
 Před nasazením řešení balíčku (.wsp), můžete vytvořit vlastní funkce a balíku pravidel ověřování k ověření, že funkce nebo balíček je platný. Například může hlásit informace, varování nebo chyby pro vývojáře k jejich vyřešení zaznamenané problémy s ověřením. Další informace najdete v tématu [jak: Vytvoření vlastní funkce a balíku ověřovacích pravidel pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).

## <a name="see-also"></a>Viz také:
- [Postupy: Spuštění kódu při provádění kroků nasazení](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)
- [Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)
- [Postupy: Vytvoření vlastní funkce a balíku ověřovacích pravidel pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)
- [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)
