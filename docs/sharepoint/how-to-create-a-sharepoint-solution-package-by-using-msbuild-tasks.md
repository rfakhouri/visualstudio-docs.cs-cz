---
title: 'Postupy: vytvoření balíčku řešení služby SharePoint pomocí úloh nástroje MSBuild | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 392724510e3145450cbea8ee70d23037ded073a1
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks"></a>Postupy: Vytvoření balíčku řešení služby SharePoint pomocí úloh nástroje MSBuild
  Můžete sestavit, vyčistit a ověřit balíček služby SharePoint (WSP) pomocí příkazového řádku úlohy nástroje MSBuild na vývojovém počítači. Můžete také používat tyto příkazy pro automatizaci procesu sestavení pomocí serveru Team Foundation Server na počítači sestavení.  
  
## <a name="building-a-sharepoint-package"></a>Vytváření balíčku služby SharePoint  
  
#### <a name="to-build-a-sharepoint-package"></a>Chcete-li vytvořit balíček služby SharePoint  
  
1.  V systému Windows **spustit** nabídce zvolte **všechny programy**, **Příslušenství**, **příkazového řádku**.  
  
2.  Přejděte do adresáře, kde se nachází projektu služby SharePoint.  
  
3.  Zadejte následující příkaz k vytvoření balíčku pro projekt. Nahraďte *ProjectFileName* s názvem projektu.  
  
    ```cmd  
    msbuild /t:Package ProjectFileName  
    ```  
  
     Například můžete spustit jeden z následujících příkazů pro balíček názvem ListDefinition1 projektu služby SharePoint.  
  
    ```cmd  
    msbuild /t:Package ListDefinition1.vbproj  
    msbuild /t:Package ListDefinition1.csproj  
    ```  
  
## <a name="cleaning-a-sharepoint-package"></a>Čištění balíček služby SharePoint  
  
#### <a name="to-clean-a-sharepoint-package"></a>Pro čištění balíček služby SharePoint  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Přejděte do adresáře, kde se nachází projektu služby SharePoint.  
  
3.  Zadejte následující příkaz k vyčištění balíčků pro projekt. Nahraďte *ProjectFileName* s názvem projektu.  
  
    ```cmd  
    msbuild /t:CleanPackage ProjectFileName  
    ```  
  
     Například můžete spustit jeden z následujících příkazů pro čištění názvem ListDefinition1 projektu služby SharePoint.  
  
    ```cmd  
    msbuild /t:CleanPackage ListDefinition1.vbproj  
    msbuild /t:CleanPackage ListDefinition1.csproj  
    ```  
  
## <a name="validating-a-sharepoint-package"></a>Ověřování balíčku služby SharePoint  
  
#### <a name="to-validate-a-sharepoint-package"></a>Chcete-li ověřit balíček služby SharePoint  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Přejděte do adresáře, kde se nachází projektu služby SharePoint.  
  
3.  Zadejte následující příkaz k ověření balíčků pro projekt. Nahraďte *ProjectFileName* s názvem projektu.  
  
    ```cmd  
    msbuild /t:ValidatePackage ProjectFileName  
    ```  
  
     Například můžete spustit jeden z následujících příkazů pro ověření názvem ListDefinition1 projektu služby SharePoint.  
  
    ```cmd  
    msbuild /t:ValidatePackage ListDefinition1.vbproj  
    msbuild /t:ValidatePackage ListDefinition1.csproj  
    ```  
  
## <a name="setting-properties-in-a-sharepoint-package"></a>Vlastnosti nastavení v balíčku služby SharePoint  
  
#### <a name="to-set-a-property-in-a-sharepoint-package"></a>Chcete-li nastavit vlastnosti v balíčku služby SharePoint  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Přejděte do adresáře, kde se nachází projektu služby SharePoint.  
  
3.  Zadejte následující příkaz pro nastavení vlastnosti v balíčku pro projekt. Nahraďte *PropertyName* s vlastností, které chcete nastavit.  
  
    ```cmd  
    msbuild /property:PropertyName=Value  
    ```  
  
     Můžete například spustit následující příkaz pro nastavení úroveň pro upozornění.  
  
    ```cmd  
    msbuild /property:WarningLevel = 2  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření funkcí služby SharePoint](../sharepoint/creating-sharepoint-features.md)   
 [Postupy: přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Postupy: Přidání a odebrání položek z funkcí služby SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  