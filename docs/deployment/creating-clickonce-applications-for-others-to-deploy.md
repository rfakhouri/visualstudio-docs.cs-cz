---
title: Vytváření aplikací ClickOnce pro ostatní nasadit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- preserved branding information
- useManifestForTrust element
- customer deployments [ClickOnce]
- multiple ClickOnce deployment and branding
- ClickOnce applications, previous .NET Framework versions
- application manifests [ClickOnce]
- <useManifestForTrust> element
- manifests [ClickOnce]
- trust applications, ClickOnce
- ClickOnce applications, deployed by others
- ClickOnce applications, previous .NET Framework
ms.assetid: d20766c7-4ef3-45ab-8aa0-3f15b61eccaa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 10f7cf3b6069c80337213283eddd12bdd54e4b7d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="creating-clickonce-applications-for-others-to-deploy"></a>Vytváření aplikací ClickOnce k implementaci dalšími osobami
Ne všechny vývojáře, kteří jsou vytvoření nasazení ClickOnce v plánu nasadit aplikace samotné. Řada z nich právě balíček své aplikace s použitím technologie ClickOnce a pak předá soubory na zákazníka, jako je například velké korporace. Zákazník bude ten, který je zodpovědný za hostování aplikace ve své síti. Toto téma popisuje některé potíže spočívající v takovýchto nasazeních ve verzích rozhraní .NET Framework verze 3.5. Popisuje pak zadaný v rozhraní .NET Framework 3.5 pomocí nové funkce "použití manifest pro vztah důvěryhodnosti" nové řešení. Nakonec dojde s doporučenou strategie pro vytvoření nasazení ClickOnce pro zákazníky, kteří stále používají starší verze rozhraní .NET Framework.  
  
## <a name="issues-involved-in-creating-deployments-for-customers"></a>Problémy při vytváření nasazení pro zákazníky  
 Několik výhrad nastane, když budete chtít zadat nasazení na zákazníka. První problém týká, podepisování kódu. Pro nasazení v síti, – manifest nasazení a manifest aplikace ClickOnce nasazení musí být podepsané pomocí digitálního certifikátu. To vydá dotaz, zda se má použít pro vývojáře nebo certifikát zákazníka při podepisování manifestů.  
  
 Jako identita aplikace ClickOnce je založena na digitální podpis manifest nasazení je důležité, dotazu, který certifikát má použít. Pokud vývojář podepisuje manifest nasazení, může vést ke konfliktu Pokud zákazník je velká společnost a více než jednoho oddělení společnosti nasadí přizpůsobenou verzi aplikace.  
  
 Řekněme například, že má společnosti Adventure Works finančního oddělení a oddělení lidských zdrojů. Obě oddělení licence aplikací ClickOnce od Microsoft Corporation, která generuje sestavy z dat uložených v databázi SQL. Microsoft poskytuje každé oddělení s verzí aplikace, které je přizpůsobené pro svá data. Pokud aplikace jsou podepsané stejným certifikátem Authenticode, uživatele, který se snaží použít pro obě aplikace by dojít k chybě, protože ClickOnce bude považovat druhou aplikaci, že je stejný jako první. V takovém případě může u zákazníka dojít nežádoucím a nepředvídatelným vedlejší účinky, které patří ke ztrátě všech dat uložených místně aplikací.  
  
 Dalším problémem vztahujícím se k podepisování kódu je `deploymentProvider` element v manifestu nasazení, který udává ClickOnce, kde má být vyhledán aktualizace aplikace. Tento element musí být přidán do manifestu nasazení před jeho podpisem. Pokud tento element je přidán později, musí být znovu podepisovat manifest nasazení.  
  
### <a name="requiring-the-customer-to-sign-the-deployment-manifest"></a>Vyžádání zákazníka k podepsání manifestu nasazení  
 Jedno řešení tohoto problému nasazení je tak, aby měl vývojáře přihlašovací manifest aplikace a zákazník podepsání manifestu nasazení. Zatímco tento přístup funguje, zavádí další problémy. Vzhledem k tomu, že certifikát Authenticode musí zůstat chráněný prostředek, nelze zákazník právě udělte certifikátu vývojáře k podepsání nasazení. Když zákazník může podepsání manifestu nasazení sami pomocí volně dostupných nástrojů sady SDK rozhraní .NET Framework, může to vyžadovat další technické znalosti, než je zákazník ochoten nebo schopen poskytnout. V takových případech obvykle vytvoří vývojář aplikací, webu nebo jiným mechanismem, pomocí kterého zákazníka můžete odeslat jejich verzi aplikace pro podepisování.  
  
### <a name="the-impact-of-customer-signing-on-clickonce-application-security"></a>Dopad podepisování zákazníka na zabezpečení aplikací ClickOnce  
 I v případě, že vývojář a zákazník Souhlasím, že zákazník má podepsání manifestu aplikace, to vyvolá jiných problémů, které obklopit identitu aplikace, zejména, která se vztahuje na nasazení důvěryhodné aplikace. (Další informace o této funkci najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).) Řekněme, že společnosti Adventure Works chce konfigurovat své klientské počítače tak, aby všechny aplikace poskytovaná společností Microsoft Corporation s úplným vztahem důvěryhodnosti. Pokud společnosti Adventure Works podepíše manifest nasazení, pak ClickOnce použije k určení úrovně důvěryhodnosti aplikace společnosti Adventure pracovní zabezpečení podpis.  
  
## <a name="creating-customer-deployments-by-using-application-manifest-for-trust"></a>Vytváření zákaznických nasazení s využitím Manifest aplikace pro vztah důvěryhodnosti  
 ClickOnce v rozhraní .NET Framework 3.5 obsahuje novou funkci, která poskytuje vývojářům a zákazníkům nové řešení pro scénář toho, jak by měla být podepsané manifesty. Manifest aplikace ClickOnce podporuje nového elementu s názvem `<useManifestForTrust>` umožňující vývojáři umožní označit, že je digitální podpis manifestu aplikace, co má být použito pro rozhodování o vztahu důvěryhodnosti. Vývojář použije nástroje balení ClickOnce – například Mage.exe, MageUI.exe a Visual Studio – k zahrňte tento prvek v manifestu aplikace, jakož i vložení jejich název vydavatele a název aplikace v manifestu.  
  
 Při použití `<useManifestForTrust>`, manifest nasazení nemusí být podepsané certifikátem Authenticode vydaný certifikační autoritou. Místo toho může být podepsané s, která se označuje jako certifikát podepsaný svým držitelem. Certifikát podepsaný svým držitelem je vytvořen zákazník nebo vývojář pomocí standardních nástrojů rozhraní .NET Framework SDK a potom se použijí na manifest nasazení pomocí nástroje pro standardní nasazení ClickOnce. Další informace najdete v tématu [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx).  
  
 Používá certifikát podepsaný svým držitelem pro manifest nasazení nabízí několik výhod. Odstraněním potřeby zákazníka získat nebo vytvořit svůj vlastní certifikát Authenticode `<useManifestForTrust>` zjednodušuje nasazení pro zákazníka, zatímco vývojáři udržovat vlastní identitu výrobce na aplikaci. Výsledkem je sada podepsaných nasazení, které jsou bezpečnější a mají jedinečné identity aplikace. Tím se eliminuje potenciální konflikt, který může nastat z nasazení stejné aplikace více zákazníků.  
  
 Podrobné informace o tom, jak vytvořit nasazení ClickOnce s `<useManifestForTrust>` povoleno, najdete v části [návod: Ruční nasazení aplikace ClickOnce této nemá není vyžadují Re-Signing a že zachovává Branding informace](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md).  
  
### <a name="how-application-manifest-for-trust-works-at-runtime"></a>Jak Manifest aplikace pro vztah důvěryhodnosti pracuje za běhu  
 Chcete-li získat lepší pochopení, jak funguje manifest aplikace pomocí vztahu důvěryhodnosti v době běhu, zvažte následující příklad. Aplikace ClickOnce, která je cílena na rozhraní .NET Framework 3.5 je vytvořena společností Microsoft. Manifest aplikace používá `<useManifestForTrust>` elementu a je podepsán společností Microsoft. Společnosti Adventure Works podepíše manifest nasazení pomocí certifikát podepsaný svým držitelem. Adventure Works, které jsou klienti nakonfigurováni tak, aby důvěřoval všechny aplikace podepsané společností Microsoft.  
  
 Když uživatel klikne na odkaz manifest nasazení, ClickOnce nainstaluje aplikace na počítači uživatele. Informace o certifikátech a nasazení Identifikujte jednoznačně aplikaci ClickOnce na klientském počítači. Pokud uživatel se pokusí znovu nainstalovat stejnou aplikaci z jiného umístění, můžete ClickOnce tuto identitu používat pro určení, zda aplikace už existuje na straně klienta.  
  
 Dále ClickOnce kontroluje Authenticode certifikát, který se používá k podepsání manifestu aplikace, která určuje úroveň důvěryhodnosti, kterou poskytne ClickOnce. Vzhledem k tomu, že společnosti Adventure Works nakonfigurovala své klientské počítače tak, aby důvěřoval všechny aplikace podepsané společností Microsoft, je tato aplikace ClickOnce udělit úplný vztah důvěryhodnosti. Další informace najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
## <a name="creating-customer-deployments-for-earlier-versions"></a>Vytváření zákaznických nasazení pro starší verze  
 Co když je vývojář nasazování aplikací ClickOnce pro zákazníky, kteří používají starší verze rozhraní .NET Framework? Následující části shrnují několik doporučených řešení, společně s výhody a nevýhody jednotlivých.  
  
### <a name="sign-deployments-on-behalf-of-customer"></a>Podepsání nasazení jménem zákazníka  
 Jedna možná strategie nasazení je pro vývojáře k vytvoření mechanismus podepsání nasazení jménem svým zákazníkům pomocí zákazníka vlastní privátní klíč. Vývojář zabrání museli spravovat privátní klíče nebo více balíčků nasazení. Vývojář poskytuje stejné nasazení u každého zákazníka. Je na zákazníkovi, chcete-li přizpůsobit pro jejich prostředí pomocí podpisové služby.  
  
 Jednou z nevýhod tato metoda je čas a náklady, které jsou nutné k implementaci. Když tato služba může být vytvořené pomocí nástrojů v sadě SDK rozhraní .NET Framework, přidá další čas vývoje do životního cyklu produktu.  
  
 Jak je uvedeno výše v tomto tématu, Další nevýhodou je, že každému zákazníkovi verzi aplikace bude mít stejnou identitu, což může vést ke konfliktu. Pokud se jedná o problém, můžete změnit na vývojáře pole název, který se používá při generování manifestu nasazení pro každou aplikaci zadejte jedinečný název. Tato akce vytvoří samostatné identity pro každou verzi aplikace a eliminovat možné konflikty identity. Toto pole odpovídá `-Name` argument pro Mage.exe a **název** na **název** ve MageUI.exe.  
  
 Řekněme například, že vývojář vytvořil aplikaci s názvem Application1. Vývojář místo vytvoření pomocí pole název nastaveným na Application1 jedno nasazení, můžete vytvořit několik nasazení s variací zákaznické na tento název, jako je například Application1-CustomerA, Application1-CustomerB a tak dále.  
  
### <a name="deploy-using-a-setup-package"></a>Nasazení pomocí instalačního balíčku  
 Druhý strategie možné nasazení je ke generování projektu Microsoft Setup k provedení počátečního nasazení aplikace ClickOnce. To lze zadat v jednom z několika různých formátů: jako nasazení MSI, pak jako spustitelný soubor (. Soubor EXE), nebo jako soubor CAB společně s dávkový skript.  
  
 Touto technikou vývojář by zadejte zákazník nasazení, která obsahuje soubory aplikace, manifest aplikace a nasazení manifestu, který slouží jako šablona. Zákazník by spusťte instalační program, který by měl vyžádat adresu URL nasazení (server nebo sdílenou složku umístění, ze kterého budou uživatelé instalovat aplikaci ClickOnce), a také digitální certifikát. Instalační program aplikace může také zvolit dotaz pro další možnosti konfigurace ClickOnce, jako je například intervalu kontroly aktualizací. Jakmile tyto informace jsou shromažďovány, instalační program by generování manifestu skutečné nasazení, podepište ho a publikování aplikace ClickOnce do umístění určený server.  
  
 Existují tři způsoby, může zákazník podepsat manifest nasazení v této situaci:  
  
1.  Zákazník může použít platný certifikát vydaný certifikační autoritou (CA).  
  
2.  Zákazník varianta na tento přístup, můžete vybrat možnost podepsání manifestu jejich nasazení se certifikát podepsaný svým držitelem. Nevýhodou je, může to způsobit aplikace zobrazíte slova "Neznámého vydavatele", když je uživatel vyzván, zda se má instalovat. Ale výhodou je, že zabrání nutnosti čas a peníze nutné certifikát vydaný certifikační autoritou menší zákazníků.  
  
3.  Nakonec vývojář může obsahovat vlastní certifikát podepsaný svým držitelem v instalační balíček. To představuje potenciální problémy s identitou aplikace uvedené výše v tomto tématu.  
  
 Nevýhodou projektu metodě instalace nasazení je čas a výdaje potřebné k vytvoření vlastního nasazení aplikace.  
  
### <a name="have-customer-generate-deployment-manifest"></a>Mít zákazníka generovat Manifest nasazení  
 Strategie třetí možné nasazení je předat pouze soubory aplikace a manifest aplikace vypnout zákazníka. V tomto scénáři zákazník zodpovídá za účelem generování a podepsání manifestu nasazení pomocí sady SDK rozhraní .NET Framework.  
  
 Nevýhodou této metody je, že vyžaduje zákazník instalace nástrojů pro rozhraní .NET Framework SDK a vývojáře nebo správce systému, který je kvalifikován k jejich použití. Někteří zákazníci mohou požadovat řešení, které vyžaduje žádné nebo téměř žádné technické úsilí z jejich strany.  
  
## <a name="see-also"></a>Viz také  
 [Nasazování aplikací ClickOnce pro testovací a produkční servery bez opětovného podpisu](../deployment/deploying-clickonce-applications-for-testing-and-production-servers-without-resigning.md)   
 [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [Návod: Ruční nasazení aplikace ClickOnce, jež nevyžaduje opětovné podepsání a které zachovává údaje o poskytovateli](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md)