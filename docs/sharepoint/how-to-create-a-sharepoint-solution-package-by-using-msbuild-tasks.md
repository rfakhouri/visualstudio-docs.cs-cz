---
title: 'Postupy: Vytvoření balíčku řešení služby SharePoint pomocí úloh nástroje MSBuild | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6f6fd87a9c666e3373515cf8df59d7cd9fd7c717
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624396"
---
# <a name="how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks"></a>Postupy: Vytvoření balíčku řešení SharePoint pomocí úloh nástroje MSBuild
  Sestavení, vyčištění a ověřit balíček Sharepointu (*.wsp*) pomocí příkazového řádku MSBuild úkoly na vývojovém počítači. Tyto příkazy můžete také použít k automatizaci procesu sestavení s použitím serveru Team Foundation Server na počítači sestavení.

## <a name="build-a-sharepoint-package"></a>Vytvořit balíček služby SharePoint

#### <a name="to-build-a-sharepoint-package"></a>Chcete-li vytvořit balíček služby SharePoint

1.  V Windows **Start** nabídce zvolte **všechny programy** > **Příslušenství** > **příkazový řádek**.

2.  Přejděte do adresáře, kde se nachází váš Sharepointový projekt.

3.  Zadejte následující příkaz pro vytvoření balíčku pro projekt. Nahraďte *ProjectFileName* s názvem projektu.

    ```cmd
    msbuild /t:Package ProjectFileName
    ```

     Můžete například spustit jednu z následujících příkazů do balíčku projektu služby SharePoint volá ListDefinition1.

    ```cmd
    msbuild /t:Package ListDefinition1.vbproj
    msbuild /t:Package ListDefinition1.csproj
    ```

## <a name="clean-a-sharepoint-package"></a>Vyčistit balíček Sharepointu

#### <a name="to-clean-a-sharepoint-package"></a>Chcete-li vyčistit balíček Sharepointu

1.  Otevřete okno příkazového řádku.

2.  Přejděte do adresáře, kde se nachází váš Sharepointový projekt.

3.  Zadejte následující příkaz k vyčištění balíčků pro projekt. Nahraďte *ProjectFileName* s názvem projektu.

    ```cmd
    msbuild /t:CleanPackage ProjectFileName
    ```

     Můžete například spustit jednu z následujících příkazů do čistého volá ListDefinition1 projektu služby SharePoint.

    ```cmd
    msbuild /t:CleanPackage ListDefinition1.vbproj
    msbuild /t:CleanPackage ListDefinition1.csproj
    ```

## <a name="validate-a-sharepoint-package"></a>Ověřit balíček Sharepointu

#### <a name="to-validate-a-sharepoint-package"></a>Chcete-li ověřit balíček Sharepointu

1.  Otevřete okno příkazového řádku.

2.  Přejděte do adresáře, kde se nachází váš Sharepointový projekt.

3.  Zadejte následující příkaz k ověření balíčku pro projekt. Nahraďte *ProjectFileName* s názvem projektu.

    ```cmd
    msbuild /t:ValidatePackage ProjectFileName
    ```

     Můžete například spustit jednu z následujících příkazů ověřte volá ListDefinition1 projektu služby SharePoint.

    ```cmd
    msbuild /t:ValidatePackage ListDefinition1.vbproj
    msbuild /t:ValidatePackage ListDefinition1.csproj
    ```

## <a name="set-properties-in-a-sharepoint-package"></a>Nastavit vlastnosti v balíčku služby SharePoint

#### <a name="to-set-a-property-in-a-sharepoint-package"></a>Nastavení vlastnosti v balíčku služby SharePoint

1.  Otevřete okno příkazového řádku.

2.  Přejděte do adresáře, kde se nachází váš Sharepointový projekt.

3.  Zadejte následující příkaz pro nastavení vlastnosti v balíčku pro projekt. Nahraďte *PropertyName* s vlastností, které chcete nastavit.

    ```cmd
    msbuild /property:PropertyName=Value
    ```

     Například můžete spustit následující příkaz, který nastavit úroveň upozornění.

    ```cmd
    msbuild /property:WarningLevel = 2
    ```

## <a name="see-also"></a>Viz také:
- [Vytvoření funkcí služby SharePoint](../sharepoint/creating-sharepoint-features.md)
- [Postupy: Přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md)
- [Postupy: Přidání a odebrání položek z funkcí služby SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)
