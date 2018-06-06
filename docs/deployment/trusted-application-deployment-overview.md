---
title: Důvěryhodné nasazení aplikací – přehled | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, install without prompting
- ClickOnce deployment, security
- trusted application deployment
ms.assetid: b24a1702-8fbe-45b1-87a0-9618a0708f1d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7bc06e106a6b42f2225668edb928e6fef7e349b
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572238"
---
# <a name="trusted-application-deployment-overview"></a>Přehled nasazení důvěryhodných aplikací
Toto téma obsahuje přehled o tom, jak nasadit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, které pomocí technologie nasazení důvěryhodných aplikací mít zvýšená oprávnění.  
  
 Nasazení důvěryhodných aplikací, součást [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] technologii nasazení usnadňuje organizacím jakékoli velikosti udělovat další oprávnění, aby spravované aplikaci bezpečnější a bezpečnější způsobem bez vyzvání uživatele. Nasazení důvěryhodné aplikace organizace právě konfigurace klientského počítače tak, aby měl seznam důvěryhodných vydavatelů, kteří jsou identifikovány pomocí certifikátů Authenticode. Poté jakákoli [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace podepsána jednu z těchto důvěryhodných vydavatelů obdrží vyšší úroveň důvěryhodnosti.  
  
> [!NOTE]
>  Důvěryhodné že nasazení aplikace vyžaduje jednorázovou konfiguraci počítače uživatele. Ve spravovaném prostředí plochy tuto konfiguraci lze provést pomocí globální zásady. Pokud nechcete pro vaši aplikaci, použijte zvýšení oprávnění. Další informace najdete v tématu [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md).  
  
## <a name="trusted-application-deployment-basics"></a>Základní informace o nasazení důvěryhodné aplikace  
 V následující tabulce jsou objekty a rolí, které se podílejí v nasazení důvěryhodných aplikací.  
  
|Objekt nebo role|Popis|  
|--------------------|-----------------|  
|Správce|Organizační entita, která je odpovědná za aktualizaci a správu klientských počítačů|  
|správce vztahu důvěryhodnosti|Subsystém v rámci modul CLR (CLR) zodpovědná za vynucení zabezpečení klientské aplikace.|  
|Vydavatele|Typ entity, která zapisuje a udržuje aplikace.|  
|Nástroje pro nasazení|Typ entity, která balíčků a distribuuje aplikace pro uživatele.|  
|certificate|Kryptografický podpis, který se skládá z veřejného a privátního klíče; obecně vydaný certifikační autoritou (CA), který zaručuje jeho pravost.|  
|Authenticode certifikátu|Certifikát s vložená metadata popisující mimo jiné používá, pro které je možné použít certifikát.|  
|certifikační autorita|Organizace, která ověřuje identitu vydavatele a vydává je certifikáty vložených s metadata vydavatele.|  
|kořenová autorita|Certifikační autorita, která autorizuje jiné certifikační autority k vystavování certifikátů.|  
|kontejner klíče|Prostor logického úložiště pro ukládání certifikátů v Microsoft Windows.|  
|důvěryhodným vydavatelem|Vydavatel, jejichž Authenticode certifikát byl přidán do seznamu důvěryhodných certifikátů (CTL) na klientském počítači.|  
  
 Větší organizace jsou často dva samostatné subjekty vydavatele a nástroje pro nasazení:  
  
-   Vydavatel je skupina, která vytvoří [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
-   Nasazovacím modulu je skupina, obvykle oddělení informačních technologií (IT), který distribuuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace na podnikové stolní počítače.  
  
 Musíte následujícím postupem využít výhod nasazení důvěryhodných aplikací:  
  
1.  Získání certifikátu pro vydavatele.  
  
2.  Přidáte vydavatele do úložiště důvěryhodných vydavatelů na všechny klienty.  
  
3.  Vytvoření vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
4.  Podepsání manifestu nasazení pomocí certifikátu vydavatele.  
  
5.  Publikujte nasazení aplikace do klientských počítačů.  
  
### <a name="obtain-a-certificate-for-the-publisher"></a>Získání certifikátu pro vydavatele  
 Digitální certifikáty jsou základní součástí Microsoft Authenticode ověřování a zabezpečení systému. Authenticode je standardní součástí operačního systému Windows. Všechny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace musí být podepsány pomocí digitálního certifikátu, bez ohledu na to, zda se účastní v nasazení důvěryhodných aplikací. Úplné vysvětlení, jak Authenticode pracuje s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], najdete v části [ClickOnce a kód Authenticode](../deployment/clickonce-and-authenticode.md).  
  
### <a name="add-the-publisher-to-the-trusted-publishers-store"></a>Přidat do úložiště důvěryhodných vydavatelů vydavatele  
 Pro vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace na příjem vyšší úroveň důvěryhodnosti, musíte přidat certifikát jako důvěryhodného vydavatele na každý klientský počítač, na kterém bude aplikace spuštěna. Provedení této úlohy je jednorázovou konfiguraci. Po jeho dokončení můžete nasadit tolik [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace podepsaný pomocí certifikátu vydavatele, jak chcete, a všechny se spustí s vysokým vztahem důvěryhodnosti.  
  
 Pokud nasazujete aplikaci ve spravovaném prostředí plochy; například je firemní intranet s operačním systémem Windows; Důvěryhodní vydavatelé můžete přidat do úložiště klienta tak, že vytvoříte nový seznam důvěryhodných certifikátů (CTL) pomocí zásad skupiny. Další informace najdete v tématu [vytvořit seznam důvěryhodných certifikátů pro objekt zásad skupiny a](http://go.microsoft.com/fwlink/?LinkId=102576).  
  
 Pokud nejsou nasazení aplikace ve spravovaném prostředí plochy, máte následující možnosti pro přidání certifikátu do úložiště důvěryhodné vydavatele:  
  
-   <xref:System.Security.Cryptography?displayProperty=fullName> Oboru názvů.  
  
-   CertMgr.exe, který je součástí aplikace Internet Explorer a proto existuje v systému Windows 98 a všechny novější verze. Další informace najdete v tématu [Certmgr.exe (nástroj Certificate Manager)](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool).  
  
### <a name="create-a-clickonce-application"></a>Vytvoření aplikace ClickOnce  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] klientskou aplikaci v kombinaci s manifestu soubory, které popisují aplikace a zadat parametry instalace. Můžete zapnout vaším programem do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí **publikovat** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Alternativně můžete vygenerovat všechny soubory potřebné pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení pomocí nástrojů, které jsou součástí [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Podrobné pokyny o [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, najdete v části [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
 Nasazení důvěryhodné aplikace je specifická pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]a lze použít pouze s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
### <a name="sign-the-deployment"></a>Podepsat nasazení  
 Po získání certifikátu, musíte ho použít k podepsání vašeho nasazení. Pokud nasazujete aplikaci pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Průvodce publikováním, průvodce bude automaticky vygenerovat zkušební certifikát pro vás Pokud nezadali jste certifikát sami. Můžete také [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno Návrhář projektu, ale k poskytnutí certifikátu Certifikační autoritou.  Viz také [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
> [!CAUTION]
>  Nedoporučujeme, že aplikace nasadit s testovacím certifikátem.  
  
 Aplikace můžete se přihlásit taky pomocí nástrojů SDK Mage.exe nebo MageUI.exe. Další informace najdete v tématu [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Úplný seznam možností příkazového řádku týkající se nasazení podepisování najdete v tématu [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
### <a name="publish-the-application"></a>Publikování aplikace  
 Jakmile jste se zaregistrovali vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty, aplikace je připravena k publikování do umístění instalace. Umístění instalace může být webový server, sdílené složky nebo na místním disku. Když klient přistupuje k manifestu nasazení poprvé, musíte zvolit správce vztahu důvěryhodnosti jestli [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace byla udělena autority nebo aby se nespouštěla na vyšší úrovni důvěryhodnosti nainstalovaného důvěryhodné vydavatele. Správce vztahu důvěryhodnosti umožňuje tuto volbu porovnání certifikátu použitého k podepsání nasazení s certifikáty uložené v důvěryhodným vydavatelem klienta úložiště. Pokud správce vztahu důvěryhodnosti najde shoda, aplikace bude spuštěna s vysokým vztahem důvěryhodnosti.  
  
## <a name="trusted-application-deployment-and-permission-elevation"></a>Nasazení důvěryhodné aplikace a zvýšení úrovně oprávnění  
 Pokud není aktuální vydavatel důvěryhodným vydavatelem, správce vztahu důvěryhodnosti pomocí zvýšení oprávnění dotázání uživatele, jestli uživatel chce, aby udělit, že vaše aplikace vyšší oprávnění. Pokud zvýšení úrovně oprávnění je zakázána správcem, ale aplikace nelze získat oprávnění ke spuštění. Aplikace se nespustí a nezobrazí se žádná oznámení pro uživatele. Další informace o zvýšení úrovně oprávnění najdete v tématu [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md).  
  
## <a name="limitations-of-trusted-application-deployment"></a>Omezení nasazení důvěryhodné aplikace  
 Nasazení důvěryhodné aplikace můžete použít k udělení zvýšené důvěryhodnosti na [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nasazené přes Web nebo prostřednictvím sdílené enterprise. Není nutné používat důvěryhodné nasazení aplikace pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace distribuované na disku CD, protože ve výchozím nastavení, tyto aplikace mají úplný vztah důvěryhodnosti.  
  
## <a name="see-also"></a>Viz také  
 [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)
