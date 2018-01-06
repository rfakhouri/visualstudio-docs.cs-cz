---
title: "Kontextové parametry | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wizards, context parameters
- context parameters
ms.assetid: 1a062dcb-8a8f-40dd-bea9-3d10f9448966
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 45c05f738086cad87d204e1421513da54a01e211
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="context-parameters"></a>Kontextové parametry
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE), můžete přidat průvodce, aby **nový projekt**, **přidat novou položku**, nebo **přidat projekt dílčí** dialogová okna. Průvodci přidané jsou k dispozici na **soubor** nabídky nebo kliknutím pravým tlačítkem na projekt v **Průzkumníku řešení**. Prostředí IDE předá kontextových parametrů k provádění průvodce. Kontextové parametry definovat stav projektu, pokud rozhraní IDE volá průvodce.  
  
 Prostředí IDE spustí Průvodce nastavením <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> Příznak volání rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> metoda pro projekt. Pokud nastavíte, musí dojít projektu `IVsExtensibility::RunWizardFile` má být spuštěna pomocí Průvodce registrovaný název nebo identifikátor GUID a dalších parametrů kontextu, které předá prostředí IDE.  
  
## <a name="context-parameters-for-new-project"></a>Kontextové parametry pro nový projekt  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`WizardType`|Registrovaný typ průvodce (<xref:EnvDTE.Constants.vsWizardNewProject>) nebo identifikátor GUID, který určuje typ průvodce. V [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] implementací, identifikátoru GUID v průvodci je {0F90E1D0-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|Řetězec, který jedinečný [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] název projektu.|  
|`LocalDirectory`|Místní umístění práce soubory projektu.|  
|`InstallationDirectory`|Cestu k adresáři [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je instalace.|  
|`FExclusive`|Logický příznak, který označuje, že projekt by měl zavřete otevřete řešení.|  
|`SolutionName`|Název souboru řešení bez části adresáře nebo .sln rozšíření. Název souboru .suo je také vytvořená pomocí `SolutionName`. Pokud tento argument není prázdný řetězec, použije průvodce <xref:EnvDTE._Solution.Create%2A> před přidáním projektu s <xref:EnvDTE._Solution.AddFromTemplate%2A>. Pokud tento název je prázdný řetězec, použijte <xref:EnvDTE._Solution.AddFromTemplate%2A> bez volání <xref:EnvDTE._Solution.Create%2A>.|  
|`Silent`|Logická hodnota, která označuje, zda se má bezobslužně spustit Průvodce jako **Dokončit** bylo kliknuto (`TRUE`).|  
  
## <a name="context-parameters-for-add-new-item"></a>Kontextové parametry pro přidání nové položky  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`WizardType`|Registrovaný typ průvodce (<xref:EnvDTE.Constants.vsWizardAddItem>) nebo identifikátor GUID, který určuje typ průvodce. V [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] implementací, identifikátoru GUID v průvodci je {0F90E1D1-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|Řetězec, který jedinečný [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] název projektu.|  
|`ProjectItems`|Místní umístění, které obsahuje pracovní soubory projektu.|  
|`ItemName`|Název položky, která má být přidán. Tento název je výchozí název souboru nebo název souboru, který uživatel zadá z **přidat položky** dialogové okno. Název je založen na příznaky, které jsou nastaveny v projektový soubor. Název může mít hodnotu null.|  
|`InstallationDirectory`|Cestu k adresáři [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je instalace.|  
|`Silent`|Logická hodnota, která označuje, zda se má bezobslužně spustit Průvodce jako **Dokončit** bylo kliknuto (`TRUE`).|  
  
## <a name="context-parameters-for-add-sub-project"></a>Kontextové parametry pro přidat dílčí projekt  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`WizardType`|Registrovaný typ průvodce (<xref:EnvDTE.Constants.vsWizardAddSubProject>) nebo identifikátor GUID, který určuje typ průvodce. V [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] implementací, identifikátoru GUID v průvodci je {0F90E1D2-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|Řetězec, který jedinečný [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] název projektu.|  
|`ProjectItems`|Ukazatel `ProjectItems` kolekce, na kterém bude průvodce pracovat. Tento ukazatel je předán na základě výběru hierarchie projektu průvodce. Uživatel obvykle vybírá do složky, do kterého chcete vložit položky a pak zavolá projektu **přidat položku** dialogové okno.|  
|`LocalDirectory`|Místní umístění práce soubory projektu.|  
|`ItemName`|Název položky, která má být přidán. Tento název je výchozí název souboru nebo název souboru, který uživatel zadá z **přidat položky** dialogové okno. Název je založen na příznaky, které jsou nastaveny v projektový soubor. Název může mít hodnotu null.|  
|`InstallationDirectory`|Cestu k adresáři [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je instalace.|  
|`Silent`|Logická hodnota, která označuje, zda se má bezobslužně spustit Průvodce jako **Dokončit** bylo kliknuto (`TRUE`).|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2>   
 [Vlastní parametry](../../extensibility/internals/custom-parameters.md)   
 [Průvodci](../../extensibility/internals/wizards.md)   
 [Průvodce (. Soubor vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)   
 [Kontextové parametry pro spuštění průvodců](http://msdn.microsoft.com/Library/051a10f4-9e45-4604-b344-123044f33a24)