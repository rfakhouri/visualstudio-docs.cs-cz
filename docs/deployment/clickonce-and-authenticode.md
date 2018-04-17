---
title: ClickOnce a kód Authenticode | Microsoft Docs
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
- .pfx files
- ClickOnce deployment, Authenticode
- Authenticode, ClickOnce
- ClickOnce deployment, certificates
- ClickOnce deployment, security
ms.assetid: ab5b6712-f32a-4e33-842f-e88ab4818ccf
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 6e4da37b0683b33396aae60a519fa4aa6b5c7e97
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="clickonce-and-authenticode"></a>ClickOnce a kód Authenticode
*Authenticode* je technologie společnosti Microsoft, která používá standardní kryptografie k podepsání kódu aplikace s digitálními certifikáty, které ověření pravosti vydavatele. Pomocí Authenticode pro nasazení aplikace, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] snižuje riziko trojského koně. Trojský kůň, není virus nebo jiný škodlivý program, který třetí strana špatně rozpozná jako legitimní program pocházející z zavedeného důvěryhodného zdroje. Podepisování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení pomocí digitálního certifikátu je volitelný krok, chcete-li ověřit, že sestavení a soubory nebylo manipulováno.  
  
 Následující části popisují různé typy digitálních certifikátů používaných v Authenticode, jak certifikáty se ověřují pomocí certifikátu autority (CA), role časového razítka v certifikátech a metody k dispozici pro úložiště certifikáty.  
  
## <a name="authenticode-and-code-signing"></a>Authenticode a podepisování kódu  
 A *digitální certifikát* je soubor, který obsahuje kryptografických veřejného a privátního klíče dvojice společně s metadat, která popisují vydavatele a kterého byl vystavený certifikát a daná agentura, která certifikát vydala.  
  
 Existují různé typy certifikátů Authenticode. Každé z nich je nakonfigurován pro různé typy přihlášení. Pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, musíte mít certifikát Authenticode, který je platný pro podepisování kódu. Pokud se pokusíte přihlásit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace s jiný typ certifikátu, jako je například e-mailu digitální certifikát, nebude fungovat. Další informace najdete v tématu [Úvod k podepisování kódu](http://go.microsoft.com/fwlink/?LinkId=179452).  
  
 Můžete získat certifikát pro podpis v jednom ze tří způsobů kódu:  
  
-   Zakupte od dodavatele certifikátu.  
  
-   Zobrazí jedna ze skupiny ve vaší organizaci, která je zodpovědná za vytváření digitálních certifikátů.  
  
-   Generovat svůj vlastní certifikát pomocí rutiny New-SelfSignedCertificate Powershellu, nebo pomocí MakeCert.exe, který je součástí [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
### <a name="how-using-certificate-authorities-helps-users"></a>Jak pomocí certifikačních autorit pomáhá uživatelům  
 Certifikát generovaný pomocí New-SelfSignedCertificate nebo nástroj MakeCert.exe se obvykle nazývá *samoobslužné cert* nebo *testovací certifikát*. Tento druh certifikátu funguje mnohem stejným způsobem, který soubor .snk funguje v rozhraní .NET Framework. Se skládá pouze z kryptografický pár veřejného a privátního klíče a neobsahuje žádné ověřitelné informace o vydavateli. Vlastní certifikáty můžete použít k nasazení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace s vysokým vztahem důvěryhodnosti v síti intranet. Pokud však tyto aplikace běží na klientském počítači, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je identifikovat jako pocházející od neznámého vydavatele. Ve výchozím nastavení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace podepsána vlastní certifikáty a nasazené přes Internet nelze využít důvěryhodné nasazení aplikace.  
  
 Naopak pokud přijetí certifikátu od certifikační Autority, například certifikát dodavatele nebo oddělení v rámci vašeho podniku certifikátu nabízí lepší zabezpečení pro vaše uživatele. Neidentifikuje jen vydavatele podepsaného softwaru, ale ověří tuto identitu kontrolou s certifikační Autoritou, který je podepsaný. Pokud certifikační Autorita není kořenovou autoritou, Authenticode také "zřetězí" zpět na kořenovou autoritou, chcete-li ověřit, že certifikační Autorita je autorizovaný k vydávání certifikátů. Pro větší zabezpečení by měl použít certifikát vystavený certifikační Autoritou, kdykoli je to možné.  
  
 Další informace o generování vlastní certifikáty najdete v tématu [New-SelfSignedCertificate](https://technet.microsoft.com/itpro/powershell/windows/pkiclient/new-selfsignedcertificate) nebo [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx).  
  
### <a name="timestamps"></a>Časová razítka  
 Certifikáty používané k podepisování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikací vyprší po určité době obvykle dvanáct měsíců. Chcete-li odstranit nutnost neustále znovu podepisovat aplikace pomocí nové certifikáty [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] podporuje časové razítko. Když je aplikace podepsána s časovým razítkem, svůj certifikát bude přijata i po vypršení platnosti, za předpokladu, že časové razítko je platný. To umožňuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] s certifikáty s vypršenou platností, ale Neplatná časová razítka, ke stažení a spuštění aplikace. Umožňuje také nainstalované aplikace s certifikáty s vypršenou platností nadále stáhnout a nainstalovat aktualizace.  
  
 Zahrnout časovým razítkem aplikační server, musí být časového razítka serveru k dispozici. Informace o tom, jak vybrat časového razítka serveru najdete v tématu [postupy: přihlášení aplikace a manifesty nasazení](../ide/how-to-sign-application-and-deployment-manifests.md).  
  
### <a name="updating-expired-certificates"></a>Aktualizace certifikáty s vypršenou platností  
 V dřívějších verzích rozhraní .NET Framework aktualizaci aplikace prošlou platností certifikátu způsobit aplikace přestane fungovat. Chcete-li vyřešit tento problém, použijte jednu z následujících metod:  
  
-   Aktualizujte rozhraní .NET Framework verze 2.0 SP1 nebo novější na systému Windows XP nebo verze 3.5 nebo později na Windows Vista.  
  
-   Tuto aplikaci odinstalujte a znovu nainstalujte novou verzi pomocí platného certifikátu.  
  
-   Vytvořte sestavení příkazového řádku, který aktualizuje certifikát. Podrobné informace o tomto procesu naleznete na [článku technické podpory Microsoft 925521](http://go.microsoft.com/fwlink/?LinkId=179454).  
  
### <a name="storing-certificates"></a>Ukládání certifikátů  
  
-   Certifikáty můžete uložit jako soubor .pfx v systému souborů nebo byste je uložit uvnitř kontejneru klíčů. Uživatel v doméně systému Windows může mít několik kontejnery klíčů. Ve výchozím nastavení MakeCert.exe uloží certifikáty do vašeho osobního kontejneru klíčů, pokud určíte, že ho měli uložit na .pfx místo. Mage.exe a MageUI.exe, [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] nástroje pro vytváření [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, umožňují použít certifikáty uložené buď způsobem.  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md)   
 [Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)