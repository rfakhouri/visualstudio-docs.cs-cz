---
title: Požadavky na nasazení aplikací | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, platform detection
- ClickOnce deployment, prerequisites
- ClickOnce deployment, dependencies
- prerequisites, ClickOnce
- dependencies, ClickOnce
ms.assetid: fc6e047e-ad94-44e8-8ff5-b6d1f4ca7735
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5fdeb1d5e543216e0cbb9cab72ecd98001caff3c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="application-deployment-prerequisites"></a>Nezbytné součásti nasazení aplikace
Zajistit, že vaše aplikace bude nainstalovat a úspěšně spuštěn, je nutné nejprve zajistit, že jsou na cílovém počítači již nainstalovány všechny součásti, na kterých je závislá vaše aplikace. Například většina aplikací vytvořených pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] jsou závislé na [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]; správnou verzi modulu CLR musí být na cílovém počítači před instalací aplikace.  
  
 Můžete vybrat tyto požadavky **dialogové okno požadavky** a nainstalujte rozhraní .NET Framework a dalších redistributables jako součást instalace. Tento postup se označuje jako *zavádění*. Dále [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generuje spustitelný program Windows s názvem Setup.exe, také známé jako *zaváděcího nástroje*. Zavaděč je odpovědná za instalaci těchto předpokladů před spuštěním vaší aplikace. Další informace o výběru těchto nezbytných podmínkách naleznete v části [dialogové okno požadavky](../ide/reference/prerequisites-dialog-box.md).  
  
 Každý požadavek má balíček zaváděcího nástroje. Balíček zaváděcího nástroje je skupina adresářů a souborů, které obsahují manifestu soubory, které popisují, jak by měly být nainstalovány požadované součásti. Pokud vaše aplikace požadavky nejsou uvedené v **požadovaných dialogové okno**, můžete vytvořit vlastní balíčky zaváděcího nástroje a přidat je do sady Visual Studio. Pak můžete vybrat požadavky **dialogové okno požadavky**. Další informace najdete v tématu [vytváření balíčků zaváděcího nástroje](../deployment/creating-bootstrapper-packages.md).  
  
 Ve výchozím nastavení je pro nasazení pomocí technologie ClickOnce povolené zavádění. Zavaděč vygenerované ClickOnce – nasazení je přihlášený. Můžete zakázat zavádění pro komponentu, ale měli byste tak učinit, pouze pokud jste si jistí, že správná verze komponenty je již nainstalován na všech cílových počítačích.  
  
## <a name="bootstrapping-and-clickonce-deployment"></a>Zavádění a ClickOnce – nasazení  
 Před instalací aplikace na klientském počítači, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] prozkoumá klientovi zkontrolujte, zda má určité požadavky uvedené v manifestu aplikace. Patří mezi ně například:  
  
-   Minimální požadovaná verze modulu CLR, který je zadán jako závislost sestavení v manifestu aplikace.  
  
-   Minimální požadovaná verze operačního systému Windows požadované aplikací, jak je uvedeno v aplikaci manifestu pomocí `<osVersionInfo>` element. (Viz [ \<závislostí > Element](../deployment/dependency-element-clickonce-application.md))  
  
-   Minimální verze všech sestavení, které musí být předinstalován v globální mezipaměti sestavení (GAC), jako je specifikováno na základě deklarace závislost sestavení v manifestu sestavení.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] může zjistit chybějící požadované součásti a požadavky můžete nainstalovat pomocí zaváděcí nástroj. Další informace najdete v tématu [postupy: instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md).  
  
> [!NOTE]
>  Ke změně hodnot v manifestech generované nástroje, jako [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a MageUI.exe, budete muset upravit manifest aplikace v textovém editoru a pak se znovu přihlaste manifestů aplikace a nasazení. Další informace najdete v tématu [postupy: opakované podepsání aplikace a manifesty nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
 Pokud používáte Visual Studio a ClickOnce k nasazení aplikace, balíčky zaváděcího nástroje, které jsou vybrány ve výchozím nastavení závisí na verzi rozhraní .NET Framework v řešení. Nicméně pokud změníte cílová verze rozhraní .NET Framework, je nutné aktualizovat možnosti v **dialogové okno požadavky** ručně.  
  
|Cílové rozhraní .NET Framework|Balíčky vybrané zaváděcího nástroje|  
|---------------------------|------------------------------------|  
|.NET Framework 4 Client Profile|.NET Framework 4 Client Profile<br /><br /> Instalační služba systému Windows verze 3.1|  
|.NET Framework 4|.NET Framework 4<br /><br /> Instalační služba systému Windows verze 3.1|  
  
 S [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, stránce Publish.htm vygenerované [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Průvodce publikování bodů buď na odkaz, který nainstaluje pouze aplikace, nebo na odkaz, který instaluje aplikace a samozaváděcí komponenty.  
  
 Pokud vygenerujete zavaděč pomocí Průvodce publikování ClickOnce nebo publikovat stránku v sadě Visual Studio, je automaticky přihlášeni Setup.exe. Pokud chcete používat vašeho zákazníka certifikát pro podepsání zavaděč, můžete však můžete později podepsání souboru.  
  
## <a name="bootstrapping-and-msbuild"></a>Zavádění a nástroje MSBuild  
 Pokud nepoužijete [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ale kompilace aplikace na příkazovém řádku, můžete vytvořit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zavádění aplikací pomocí Microsoft Build Engine (MSBuild) úlohy. Další informace najdete v tématu [GenerateBootstrapper – úloha](../msbuild/generatebootstrapper-task.md).  
  
 Jako alternativu k zavedení spouštěcího programu můžete předem nasadit komponent pomocí systému distribuce elektronického software, jako je například Microsoft Systems Management Server (SMS).  
  
## <a name="bootstrapper-setupexe-command-line-arguments"></a>Argumenty příkazového řádku (Setup.exe) zaváděcího nástroje  
 Setup.exe generované [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a úlohy nástroje MSBuild podporuje následující malou sadu argumentů příkazového řádku. Všechny argumenty zadané zaváděcí aplikace nad rámec těchto předají se instalační program aplikace.  
  
 Pokud změníte žádné možnosti zaváděcího nástroje, musíte změnit bez znaménka zaváděcího nástroje a potom se přihlaste soubor zaváděcího nástroje později.  
  
|Argument příkazového řádku|Popis|  
|---------------------------|-----------------|  
|**-?, -h, – Nápověda**|Zobrazí dialogové okno nápovědy.|  
|**-adresu url, - componentsurl**|Zobrazí uložené adresy URL a adresy url komponent pro toto nastavení.|  
|**-Adresa url =** `location`|Nastaví adresu URL, kde bude hledat Setup.exe [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.|  
|**-componentsurl =** `location`|Nastaví adresu URL, kde Setup.exe bude vypadat závislosti, jako [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].|  
|**-homesite =** `true`**&#124;** `false`|Když `true`, stáhne závislosti z upřednostňovaných umístění na webu dodavatele. Přepíše **- componentsurl** nastavení. Když `false`, stáhne závislosti z adresu URL zadanou v **- componentsurl**.|  
  
## <a name="operating-system-support"></a>Podpora operačního systému  
 Zaváděcího nástroje Visual Studio není podporována v systému Windows Server 2008 Server Core nebo Windows Server 2008 R2 jádra serveru, který poskytuje nízká údržba serveru prostředí s omezenou funkčností. Možnost instalace jádra serveru podporuje například pouze do profilu rozhraní .NET Framework 3.5 Server Core, takže funkce sady Visual Studio, které závisí na celý rozhraní .NET Framework nelze spustit.  
  
## <a name="see-also"></a>Viz také  
 [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)