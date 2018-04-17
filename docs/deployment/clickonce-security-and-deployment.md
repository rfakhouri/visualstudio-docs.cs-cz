---
title: ClickOnce – zabezpečení a nasazení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployment
- deploying applications [ClickOnce]
- ClickOnce deployment
- publishing, ClickOnce
ms.assetid: abab6d34-c3c2-45c1-a8b6-43c7d3131e7a
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 24ebab9776c6cb0b829e1b79cb089ef6b826f726
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="clickonce-security-and-deployment"></a>ClickOnce – zabezpečení a nasazení
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je nasazení technologie, která umožňuje vytvoření automatických aktualizací aplikací systému Windows, které můžete nainstalovat a spustit s minimálním uživatelským interakci. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] poskytuje úplnou podporu pro publikování a aktualizace aplikace nasazené pomocí technologie ClickOnce, pokud jste si vytvořili projekt v jazyce Visual Basic a Visual C#. Další informace o nasazení aplikací Visual C++, najdete v části [ClickOnce – nasazení pro aplikace Visual C++](/cpp/ide/clickonce-deployment-for-visual-cpp-applications).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení předchází tři hlavní problémy v nasazení:  
  
-   **Problémy při aktualizaci aplikace.** Pomocí nasazení Instalační služby systému Windows při každé aktualizaci aplikace, uživatel může nainstalovat aktualizaci, soubor msp a použijte ho pro nainstalovaný produkt; s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, můžete poskytnout aktualizace automaticky. Staženy pouze ty části aplikace, které se změnily, a pak je plná aktualizovaná aplikace přeinstalovat z novou složku vedle sebe.  
  
-   **Dopad na počítači uživatele.** Pomocí nasazení Instalační služby systému Windows aplikace často spoléhají na sdílené součásti s potenciálními konflikty správy verzí; s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, každá aplikace je samostatná a nemůže konfliktu s jinými aplikacemi.  
  
-   **Oprávnění zabezpečení.** Instalační služba systému Windows vyžaduje oprávnění správce a umožňuje jenom omezené uživatele instalaci; [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení umožňuje uživatelům bez oprávnění správce k instalaci a uděluje pouze ty zabezpečení přístupu kódu nezbytná oprávnění pro aplikaci.  
  
 V minulosti se k těmto problémům může někdy dojít vývojářům rozhodnout o vytvoření webové aplikace namísto aplikace pro systém Windows, zachovávají bohaté uživatelské rozhraní pro usnadnění instalace. Pomocí aplikace nasazené pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], může mít nejlepší z obou technologií.  
  
## <a name="what-is-a-clickonce-application"></a>Co je aplikace ClickOnce?  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace je Windows Presentation Foundation (.xbap), Windows Forms (.exe), konzolová aplikace (.exe) nebo řešení Office (.dll) publikována pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] technologie. Můžete publikovat [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace třemi různými způsoby: z webové stránky, ze síťové sdílené složky nebo z média, například na disku CD-ROM. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace může být nainstalovaný na počítači koncového uživatele a spustit místně i v případě, že je počítač v režimu offline, nebo ho můžete spustit v režimu pouze online bez trvale nic instalace na počítači koncového uživatele. Další informace najdete v tématu [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace může být automatických aktualizací; může vyhledat novější verze, které jsou k dispozici a automaticky nahradit všechny aktualizované soubory. Vývojář může určit chování aktualizací; Správce sítě a můžete také ovládat strategie, například označení aktualizace jako povinné aktualizace. Aktualizace můžete také vrátit zpět na starší verzi koncový uživatel nebo správce. Další informace najdete v tématu [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
 Protože [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace jsou izolovány instalaci nebo spuštění [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nelze přerušit stávající aplikace. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace jsou samostatné; Každý [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace je nainstalována do a spustit z zabezpečené na uživatele, mezipaměti každou aplikaci. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace spustit v zónách zabezpečení Internetu nebo intranetu. V případě potřeby aplikace může požadovat zvýšená oprávnění. Další informace najdete v tématu [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md).  
  
## <a name="how-clickonce-security-works"></a>Jak funguje zabezpečení ClickOnce  
 Základní [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zabezpečení je založena na certifikáty, zásady zabezpečení přístupu kódu a vztahu důvěryhodnosti ClickOnce.  
  
### <a name="certificates"></a>Certifikáty  
 Authenticode certifikáty se používají k ověření pravosti vydavatele. Pomocí Authenticode pro nasazení aplikace ClickOnce pomáhá zabránit škodlivý program vydávání sama sebe jako legitimní program pocházející z zavedeného důvěryhodného zdroje. Volitelně můžete certifikáty lze také použít k podepsání aplikace a manifesty nasazení k prokázání, že soubory nebylo manipulováno. Další informace najdete v tématu [ClickOnce a kód Authenticode](../deployment/clickonce-and-authenticode.md). Certifikáty lze také nakonfigurovat klientské počítače tak, aby měl seznam důvěryhodných vydavatelů. Pokud aplikace pochází z důvěryhodného vydavatele, lze nainstalovat bez nutnosti zásahu uživatele. Další informace najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
### <a name="code-access-security"></a>Zabezpečení přístupu kódu  
 Zabezpečení přístupu kódu pomáhá omezit přístup, který má kód k chráněným prostředkům. Ve většině případů můžete omezit oprávnění zón Internetu nebo místní Intranet. Použití **zabezpečení** stránky v **ProjectDesigner** k vyžádání oblasti vhodné pro aplikaci. Můžete také ladit aplikace s omezenými oprávněními emulovat činnost koncového uživatele. Další informace najdete v tématu [zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).  
  
### <a name="clickonce-trust-prompt"></a>Vztahu důvěryhodnosti ClickOnce  
 Pokud aplikace vyžaduje další oprávnění než povoluje zóny, koncový uživatel může vyzváni k rozhodnutí o vztahu důvěryhodnosti. Koncový uživatel může rozhodnout, pokud jsou důvěryhodné pro spuštění aplikace ClickOnce, jako je například formulářových aplikací Windows, aplikace Windows Presentation Foundation, konzolové aplikace, aplikace prohlížeče XAML a řešení pro systém Office. Další informace najdete v tématu [postupy: Konfigurace výzva chování vztahu důvěryhodnosti ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md).  
  
## <a name="how-clickonce-deployment-works"></a>Jak funguje ClickOnce – nasazení  
 Základní [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení architektura je založená na dva soubory manifestu XML: manifest aplikace a manifest nasazení. Soubory se používají k popisu nainstalovanou aplikací ClickOnce z, jak jsou aktualizovány a když jsou aktualizovány.  
  
### <a name="publishing-clickonce-applications"></a>Publikování aplikací ClickOnce  
 Manifest aplikace popisuje vlastní aplikace. To zahrnuje sestavení, závislosti a soubory, které tvoří aplikace, požadovaná oprávnění a umístění, kde budou k dispozici aktualizace. Vývojář aplikace vydává manifest aplikace pomocí Průvodce publikování v sadě Visual Studio nebo generování manifestu a nástroj pro úpravy (Mage.exe) v [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
 Manifest nasazení popisuje, jak je aplikace nasazená. To zahrnuje umístění manifestu aplikace a verze aplikace, která by měla spouštět klienti.  
  
### <a name="deploying-clickonce-applications"></a>Nasazení aplikace ClickOnce  
 Po vytvoření, manifest nasazení zkopírován do umístění nasazení. To může být webového serveru, síťové sdílené složky nebo média, například z disku CD. Manifest aplikace a všechny soubory aplikace jsou také zkopírují do umístění nasazení, který je uveden v manifestu nasazení. To může být stejný jako umístění nasazení, nebo může být do jiného umístění. Při použití **Průvodci publikováním** v sadě Visual Studio, operace kopírování probíhají automaticky.  
  
### <a name="installing-clickonce-applications"></a>Instalace aplikace ClickOnce  
 Po jeho nasazení do umístění nasazení, můžete koncovým uživatelům stáhnout a nainstalovat aplikaci kliknutím na ikonu představující soubor manifestu nasazení na webové stránce nebo ve složce. Ve většině případů koncový uživatel předloží jednoduché dialogové okno s dotazem uživatele k potvrzení instalace, po kterém instalace pokračuje a spuštění aplikace bez dalšího zásahu. V případech, kdy aplikace vyžaduje zvýšená oprávnění nebo pokud aplikace není podepsán důvěryhodným certifikátem dialogové okno také požádá uživatele a udělit oprávnění, než mohla pokračovat instalace. I když instalace ClickOnce jsou jednotlivé uživatele, zvýšení úrovně oprávnění může být požadováno, pokud jsou požadované součásti, které vyžadují oprávnění správce. Další informace o zvýšenými oprávněními, najdete v části [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md).  
  
 Certifikáty může být důvěryhodná na úrovni počítače nebo organizace, tak, aby aplikace ClickOnce podepsány důvěryhodným certifikátem může tichou instalaci. Další informace o důvěryhodných certifikátů najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
 Aplikace mohou být přidány do uživatele **spustit** nabídky a **přidat nebo odebrat programy** v **ovládací panely**. Na rozdíl od jiných technologií nasazení není nic přidáno do **Program Files** se vyžadují pro instalaci složky nebo registru a žádná administrativní práva  
  
> [!NOTE]
>  Je také možné zabránit aplikaci se přidává do **spustit** nabídky a **přidat nebo odebrat programy** skupiny, ve skutečnosti chová jako webovou aplikaci. Další informace najdete v tématu [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
### <a name="updating-clickonce-applications"></a>Aktualizace aplikací ClickOnce  
 Když vývojáři aplikace vytvořit aktualizovaná verze aplikace, vygenerovat nový manifest aplikace a zkopírujte soubory do umístění nasazení – obvykle na stejné úrovni jako složku pro původní složky pro nasazení aplikace. Správce aktualizuje manifest nasazení tak, aby odkazovaly do umístění nové verze aplikace.  
  
> [!NOTE]
>  **Průvodci publikováním** v sadě Visual Studio můžete použít k provedení těchto kroků.  
  
 Kromě umístění nasazení manifest nasazení také obsahuje na aktualizace umístění (webové stránky nebo síťové sdílené složky), kde je aplikace zkontroluje aktualizovaných verzí. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] **Publikování** vlastnosti slouží k určení, kdy a jak často by měla aplikace vyhledat aktualizace. Chování aktualizací lze zadat v manifestu nasazení, nebo ji lze zobrazit jako volby uživatele v uživatelském rozhraní aplikace pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] rozhraní API. Kromě toho **publikovat** vlastnosti mohou být použity pro nastavení aktualizací povinné nebo se vrátit zpět starší verze. Další informace najdete v tématu [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
### <a name="third-party-installers"></a>Instalační programy třetích stran  
 Můžete přizpůsobit instalačním programem vaší ClickOnce k instalaci komponenty jiných výrobců společně s vaší aplikace. Musí mít redistribuovatelného balíčku (soubor .exe nebo .msi) a Popis balíčku s manifestu produktu jazykově neutrální a manifestu balíčku konkrétní jazyk. Další informace najdete v tématu [vytváření balíčků zaváděcího nástroje](../deployment/creating-bootstrapper-packages.md).  
  
## <a name="clickonce-tools"></a>Nástroje pro ClickOnce  
 V následující tabulce jsou uvedeny nástroje, můžete použít k vygenerování, upravit, podepisování a nové podepsání manifestů aplikace a nasazení.  
  
|Nástroj|Popis|  
|----------|-----------------|  
|[Stránka Zabezpečení, Návrhář projektu](../ide/reference/security-page-project-designer.md)|Přihlásí manifestů aplikace a nasazení.|  
|[Stránka Publikovat, Návrhář projektu](../ide/reference/publish-page-project-designer.md)|Vytváří a upravuje manifestů aplikace a nasazení pro aplikace Visual Basic a Visual C#.|  
|[Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)|Generuje manifestů aplikace a nasazení pro aplikace Visual Basic, Visual C# a Visual C++.<br /><br /> Podepíše a znovu podepíše manifestů aplikace a nasazení.<br /><br /> Můžete spustit z dávky skripty a příkazového řádku.|  
|[MageUI.exe (Manifest Generation and Editing Tool, grafický klient)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)|Vytváří a upravuje manifestů aplikace a nasazení.<br /><br /> Podepíše a znovu podepíše manifestů aplikace a nasazení.|  
|[GenerateApplicationManifest – úloha](../msbuild/generateapplicationmanifest-task.md)|Generuje manifest aplikace.<br /><br /> Můžete spustit z nástroje MSBuild. Další informace najdete v tématu [MSBuild – Reference](../msbuild/msbuild-reference.md).|  
|[GenerateDeploymentManifest – úloha](../msbuild/generatedeploymentmanifest-task.md)|Generuje manifest nasazení.<br /><br /> Můžete spustit z nástroje MSBuild. Další informace najdete v tématu [MSBuild – Reference](../msbuild/msbuild-reference.md).|  
|[SignFile – úloha](../msbuild/signfile-task.md)|Přihlásí manifestů aplikace a nasazení.<br /><br /> Můžete spustit z nástroje MSBuild. Další informace najdete v tématu [MSBuild – Reference](../msbuild/msbuild-reference.md).|  
|<xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities>|Vytvořte vlastní aplikaci pro generování manifestů aplikace a nasazení.|  
  
 Následující tabulka uvádí verze rozhraní .NET Framework, které jsou potřeba pro podporu aplikací ClickOnce v těchto prohlížečů.  
  
|Prohlížeč|Verze rozhraní .NET Framework|  
|-------------|----------------------------|  
|Internet Explorer|2.0, 3.0, 3.5, 3.5 SP1, 4|  
|Firefox|2.0 SP1, 3.5 SP1, 4|  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – nasazení v systému Windows Vista](../deployment/clickonce-deployment-on-windows-vista.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Nasazování komponent COM s ClickOnce](../deployment/deploying-com-components-with-clickonce.md)   
 [Vytváření aplikací ClickOnce z příkazového řádku](../deployment/building-clickonce-applications-from-the-command-line.md)   
 [Ladění aplikací ClickOnce používajících System.Deployment.Application](../deployment/debugging-clickonce-applications-that-use-system-deployment-application.md)