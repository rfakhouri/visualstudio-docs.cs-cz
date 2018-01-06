---
title: "Postupy: Konfigurace projektů pro více cílových platforem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], targeting platforms
- platforms, changing target platforms
ms.assetid: affa2392-7aed-45ac-9ffa-1d8e0496d590
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7686e792d804af85bb8f9588f3ae78fd6b6ec3e3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-projects-to-target-multiple-platforms"></a>Postupy: Konfigurace projektů pro více cílových platforem
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]poskytuje způsob, jak řešení cílit na několik různých architektury procesoru, nebo platformy, najednou. Chcete-li nastavit tyto vlastnosti jsou přístupné prostřednictvím **nástroje Configuration Manager** dialogové okno.  
  
## <a name="targeting-a-platform"></a>Cílení platformy  
 **Nástroje Configuration Manager** dialogové okno umožňuje vytvořit a nastavit úroveň řešení a projektu konfigurace a platformy. Každou kombinaci řešení úrovni konfigurace a cíle může mít jedinečnou sadu vlastnosti související s, což umožňuje snadno přepínat mezi, například konfigurace verze s cílem [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)] platformy, konfigurace verze která se zaměřuje x86 platformy a konfiguraci ladění, která je cílena x86 platformy.  
  
#### <a name="to-set-your-configuration-to-target-a-different-platform"></a>Chcete-li nastavit konfiguraci pro jinou platformu  
  
1.  Na **sestavení** nabídky, klikněte na tlačítko **nástroje Configuration Manager**.  
  
2.  V **aktivním řešení platformy pole**, vyberte platformu řešení k cíli, nebo vyberte  **\<nový >** k vytvoření nové platformě. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]bude vaše aplikace pro platformu, která je nastavena jako aktivní platformy v kompilaci **nástroje Configuration Manager** dialogové okno.  
  
## <a name="removing-a-platform"></a>Odebrání platformu  
 Pokud si myslíte, že nemáte žádné požadavky pro platformu, můžete ho pomocí dialogového okna nástroje Configuration Manager odebrat. Tato akce odebere všechna nastavení řešení a projektů, které jste nakonfigurovali pro tuto kombinaci konfigurace a cíle.  
  
#### <a name="to-remove-a-platform"></a>Chcete-li odebrat platformu  
  
1.  Na **sestavení** nabídky, klikněte na tlačítko **nástroje Configuration Manager**.  
  
2.  V **aktivním řešení platformy pole**, vyberte  **\<Upravit >**. **Upravit platformy řešení** otevře se dialogové okno.  
  
3.  Klikněte na platformu, kterou chcete odebrat a klikněte na **odebrat**.  
  
## <a name="targeting-multiple-platforms-with-one-solution"></a>Cílení na více platforem s jedno řešení  
 Protože můžete změnit nastavení založené na kombinaci konfigurace a nastavení platformy, můžete nastavit řešení, který může cílit na více než jedné platformě.  
  
#### <a name="to-target-multiple-platforms"></a>Pro více cílových platforem  
  
1.  Použití **nástroje Configuration Manager** přidat alespoň dvě cílové platformy pro řešení.  
  
2.  Vyberte platformu, kterou chcete zacílit z **platforma Active řešení** seznamu.  
  
3.  Sestavte řešení.  
  
#### <a name="to-build-multiple-solution-configurations-at-once"></a>K sestavení více konfigurací řešení najednou  
  
1.  Použití **nástroje Configuration Manager** přidat alespoň dvě cílové platformy pro řešení.  
  
2.  Použití **dávkové sestavení** okno vytvořit několik konfigurace řešení najednou.  
  
 Je možné, že na úrovni řešení platformě nastavení, například [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)], a mít žádné projekty v rámci tohoto řešení cílení na stejnou platformu. Je také možné, že více projektů ve vašem řešení, každý cílení na různých platformách. Doporučuje se, že pokud máte jeden z těchto situací, můžete vytvořit novou konfiguraci s popisný název, aby nedocházelo k záměně.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)   
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [Sestavování a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)