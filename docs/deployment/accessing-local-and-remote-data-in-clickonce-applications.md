---
title: Přístup k místním i vzdáleným datům v aplikacích ClickOnce | Microsoft Docs
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
- ClickOnce deployment, data
- data access, ClickOnce applications
ms.assetid: be5cbe12-6cb6-49c9-aa59-a1624e1eef3d
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: ffa0ebae820e5f7c62dc60e3d9bde06b206ed29b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="accessing-local-and-remote-data-in-clickonce-applications"></a>Přístup k lokálním a vzdáleným datům v aplikacích ClickOnce
Většina aplikací spotřebovávají nebo tvoří data. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] poskytuje celou řadu možností pro čtení a zápis dat, místně i vzdáleně.  
  
## <a name="local-data"></a>Místní Data  
 S [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], můžete načíst a ukládat data místně pomocí jedné z následujících metod:  
  
-   [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Datový adresář  
  
-   Izolované úložiště  
  
-   Jiné místní soubory  
  
### <a name="clickonce-data-directory"></a>Adresář dat ClickOnce  
 Každý [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nainstalována na místním počítači má datový adresář, který je uložen ve složce Dokumenty a nastavení uživatele. Všechny soubory součástí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace a označena jako soubor "data" je zkopírován do tohoto adresáře při instalaci aplikace. Datové soubory mohou být jakéhokoli typu souboru, nejčastěji používají se text, XML a soubory databáze jako jsou například soubory .mdb Microsoft Access.  
  
 Datový adresář je určen pro data spravovaná aplikace, který jsou data, která aplikace explicitně ukládá a udržuje. Všechny statické nezávislé soubory nejsou označeny jako "data" v manifestu aplikace bude místo toho jsou umístěny v adresáři aplikace. Tento adresář je, kde jsou umístěny spustitelné soubory (.exe) a sestavení aplikace.  
  
> [!NOTE]
>  Když [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] odinstalaci aplikace, je taky odstranit adresář jeho Data. Nikdy nepoužívejte datový adresář k uložení dat řízená na koncových uživatelů, jako jsou dokumenty.  
  
#### <a name="marking-data-files-in-a-clickonce-distribution"></a>Označení datové soubory v distribuci ClickOnce  
 Chcete-li vložit existující soubor do adresáře dat, je třeba označit existující soubor jako datový soubor v vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace souboru manifestu aplikace. Další informace najdete v tématu [postupy: zahrnutí datového souboru v aplikaci ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
#### <a name="reading-from-and-writing-to-the-data-directory"></a>Čtení a zápis dat adresáře  
 Čtení z datového adresáře vyžaduje, aby vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] žádostí na aplikace oprávnění ke čtení; podobně zápisu do adresáře vyžaduje oprávnění k zápisu. Vaše aplikace bude mít tato oprávnění automaticky, pokud je nakonfigurovaná pro spuštění s úplný vztah důvěryhodnosti. Další informace o zvyšování oprávnění pro vaši aplikaci pomocí zvýšení úrovně oprávnění nebo nasazení důvěryhodných aplikací najdete v tématu [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md).  
  
> [!NOTE]
>  Pokud vaše organizace nepoužívá nasazení důvěryhodných aplikací a má vypnout zvýšení úrovně oprávnění, potvrzující oprávnění se nezdaří.  
  
 Po aplikaci má tato oprávnění, má přístup do adresáře dat pomocí volání metody třídy v rámci <xref:System.IO>. Můžete získat cesta do adresáře dat v rámci Windows Forms [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí <xref:System.Deployment.Application.ApplicationDeployment.DataDirectory%2A> vlastnost definovanou u <xref:System.Deployment.Application.ApplicationDeployment.CurrentDeployment%2A> vlastnost <xref:System.Deployment.Application.ApplicationDeployment>. To je nejpohodlnější a doporučený způsob pro přístup k datům. Následující příklad kódu ukazuje, jak to udělat pro textový soubor s názvem CSV.txt, který jste zahrnuli ve vašem nasazení jako datový soubor.  
  
 [!code-csharp[ClickOnce.OpenDataFile#1](../deployment/codesnippet/CSharp/accessing-local-and-remote-data-in-clickonce-applications_1.cs)]
 [!code-vb[ClickOnce.OpenDataFile#1](../deployment/codesnippet/VisualBasic/accessing-local-and-remote-data-in-clickonce-applications_1.vb)]  
  
 Další informace o označení souborů ve vašem nasazení jako datové soubory, najdete v části [postupy: zahrnutí datového souboru v aplikaci ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
 Taky můžete získat pomocí příslušných proměnných na cestu k adresáři data <xref:System.Windows.Forms.Application> třídy, jako například <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A>.  
  
 Manipulace s další typy souborů může vyžadovat další oprávnění. Například pokud chcete používat soubor Access databáze (.mdb), aplikace musí uplatnit úplný vztah důvěryhodnosti pro použití příslušných <xref:System.Data> třídy.  
  
#### <a name="data-directory-and-application-versions"></a>Datový adresář a verze aplikace  
 Každá verze aplikace má vlastní datový adresář, který je izolován od ostatních verzí. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vytvoří tento adresář bez ohledu na to, jestli jsou všechny datové soubory zahrnuté v nasazení tak, že aplikace má umístění pro vytvoření nové datové soubory v době běhu. Při instalaci nové verze aplikace [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zkopíruje všechny existující soubory data z předchozí verze datového adresáře do adresáře dat novou verzi – jestli byly zahrnuty do původního nasazení nebo vytvořený aplikace.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nahradí starší verzi souboru novější verzi serveru datový soubor má hodnotu hash různých v předchozí verzi aplikace jako novou verzi. Navíc pokud starší verzi aplikace vytvořila nový soubor, který má stejný název jako soubor součástí nasazení nové verze, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] přepíše soubor staré verze pomocí nového souboru. V obou případech staré soubory zahrnuty v podadresáři uvnitř do adresáře dat s názvem `.pre`, takže aplikace nepřijdou o přístup stará data pro účely migrace.  
  
 Pokud potřebujete citlivější přenesení dat, můžete použít [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] rozhraní API nasazení k provedení vlastní migrace z původního datového adresáře do nového adresáře Data. Budete muset otestovat dostupnost stažení pomocí <xref:System.Deployment.Application.ApplicationDeployment.IsFirstRun%2A>, stáhnout aktualizace pomocí <xref:System.Deployment.Application.ApplicationDeployment.Update%2A> nebo <xref:System.Deployment.Application.ApplicationDeployment.UpdateAsync%2A>, a provést vlastní migrace dat fungovat vlastní po aktualizaci po dokončení.  
  
### <a name="isolated-storage"></a>Izolované úložiště  
 Izolované úložiště poskytuje rozhraní API pro vytváření a přístup k souborům pomocí jednoduché rozhraní API. Skutečné umístění uložených souborů skrytá vývojář i uživatele.  
  
 Izolované úložiště funguje ve všech verzích [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Izolované úložiště funguje taky v částečně důvěryhodné aplikace bez nutnosti uděluje další oprávnění. Izolované úložiště byste měli použít, pokud vaše aplikace musíte spustit v částečné důvěryhodnosti, ale musí spravovat data specifické pro aplikaci.  
  
 Další informace najdete v tématu [izolované úložiště](/dotnet/standard/io/isolated-storage).  
  
### <a name="other-local-files"></a>Jiné místní soubory  
 Pokud vaše aplikace musí fungovat s nebo uložit data koncových uživatelů, jako jsou sestavy, obrázky, Hudba a tak dále, vaše aplikace bude vyžadovat <xref:System.Security.Permissions.FileIOPermission> ke čtení a zápisu dat do místního systému souborů.  
  
## <a name="remote-data"></a>Vzdálená Data  
 V určitém okamžiku bude pravděpodobně mít vaše aplikace k načtení informací ze vzdáleného webu, jako je například zákazníka nebo obchodní informace. Tato část popisuje nejběžnější postupy pro načítání vzdálených dat.  
  
### <a name="accessing-files-by-using-http"></a>Přístup k souborům pomocí protokolu HTTP  
 Můžete přistupujete k datům z webového serveru pomocí <xref:System.Net.WebClient> nebo <xref:System.Net.HttpWebRequest> třídy v <xref:System.Net> oboru názvů. Data mohou být buď statické soubory nebo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace, které vracejí nezpracovaný text nebo XML data. Pokud vaše data jsou ve formátu XML, je nejrychlejší způsob, jak načíst data pomocí <xref:System.Xml.XmlDocument> třídy, jehož <xref:System.Xml.XmlDocument.Load%2A> metoda přebírá adresu URL jako argument. Příklad, naleznete v části [čtení dokumentu XML do modelu DOM](/dotnet/standard/data/xml/reading-an-xml-document-into-the-dom).  
  
 Je nutné zvážit zabezpečení, když vaše aplikace přistupuje k vzdálených dat prostřednictvím protokolu HTTP. Ve výchozím vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace přístup k síťovým prostředkům, může být omezená, v závislosti na tom, jak byla aplikace nasazena. Aby se zabránilo škodlivé programy v získání přístupu k privilegovaným vzdáleným datům nebo pomocí počítači uživatele k útoku na jiné počítače v síti se vztahují tyto omezení.  
  
 Následující tabulka uvádí strategie nasazení, které můžete použít a jejich výchozí webová oprávnění.  
  
|Typ nasazení|Výchozí síťová oprávnění|  
|---------------------|---------------------------------|  
|Instalace webové|Můžete pouze přístup k webovému serveru, ze kterého byla aplikace nainstalována|  
|Instalace ze sdílené složky|Nelze získat přístup k webové servery|  
|Instalace CD-ROM|Můžete přistupovat na webové servery|  
  
 Pokud vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nemůže v důsledku omezení zabezpečení přístup k webovému serveru, musí aplikace assert <xref:System.Net.WebPermission> pro tento web. Další informace o zvýšení oprávnění zabezpečení pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, najdete v části [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md).  
  
### <a name="accessing-data-through-an-xml-web-service"></a>Přístup k datům prostřednictvím webové služby XML  
 Pokud jste vystavit data jako webové služby XML, můžete přístup k datům pomocí proxy serveru XML webové služby. Proxy server je [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] třídy můžete vytvořit buď pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Operace webové služby XML – například načítání zákazníků, uvádění objednávek a tak dále – jsou zveřejněné jako metody na proxy serveru. Díky tomu mnohem jednodušší než nezpracovaný text nebo soubory XML webové služby.  
  
 Pokud vaše webová služba XML působí přes protokol HTTP, služba bude vázána stejná omezení zabezpečení, jako <xref:System.Net.WebClient> a <xref:System.Net.HttpWebRequest> třídy.  
  
### <a name="accessing-a-database-directly"></a>Přístup k databázi  
 Můžete použít tříd v rámci <xref:System.Data> oboru názvů k vytvoření přímé připojení k serveru databáze, jako je SQL Server v síti, ale musí odpovídat problémy se zabezpečením. Na rozdíl od požadavků protokolu HTTP jsou žádosti o připojení databáze vždy zakázané ve výchozím nastavení v částečné důvěryhodnosti; můžete pouze taková oprávnění budete mít ve výchozím nastavení při instalaci vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace z disku CD-ROM. To dává úplný vztah důvěryhodnosti vaší aplikaci. Pokud chcete povolit přístup ke konkrétní databázi systému SQL Server, vaše aplikace musí požádat <xref:System.Data.SqlClient.SqlClientPermission> k němu; pro povolení přístupu k databázi než SQL Server, musíte požádat o <xref:System.Data.OleDb.OleDbPermission>.  
  
 Ve většině případů, nebudete mít pro přístup k databázi přímo, ale bude přistupovat místo prostřednictvím serveru webové aplikace napsané v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] nebo webové služby XML. Přístup k databázi tímto způsobem je často nejlepší metody Pokud vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace z webového serveru. Server v částečné důvěryhodnosti můžete přistupovat bez zvyšování oprávnění aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Zahrnutí datového souboru do aplikace ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)