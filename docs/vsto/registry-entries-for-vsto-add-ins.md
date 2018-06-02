---
title: Položky registru pro doplňky VSTO
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- LoadBehavior entry
- add-ins [Office development in Visual Studio], registry entries
- registry keys [Office development in Visual Studio]
- application-level add-ins [Office development in Visual Studio], registry entries
- registry entries [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e2aaec6df10a39d9f07938502a30eaa0a5d4ee9d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692893"
---
# <a name="registry-entries-for-vsto-add-ins"></a>Položky registru pro doplňky VSTO
  Když nasadíte doplňků VSTO vytvořené pomocí sady Visual Studio, musíte vytvořit konkrétní sady položek registru. Tyto položky registru poskytují informace, které umožní aplikaci Microsoft Office ke zjištění a načíst doplňku VSTO.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Při sestavování projektu sady Visual Studio vytváří tyto položky registru na vývojovém počítači, takže můžete snadno spustit a ladění doplňku VSTO. Pokud používáte ClickOnce k nasazení vašeho doplňku VSTO, položky registru jsou automaticky vytvoří na počítači koncového uživatele. Pokud používáte k nasazení vašeho doplňku VSTO Instalační služby systému Windows, musíte nakonfigurovat InstallShield Limited Edition projektu pro vytvoření položky registru v počítači koncového uživatele.  
  
 Další informace o tom, jak se položky registru používají během procesu načítání pro doplňky VSTO najdete v tématu [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
> [!NOTE]  
>  V tomto tématu se text *ID doplněk* představuje jedinečné ID pro váš doplňku VSTO. Ve výchozím nastavení ID je název vašeho sestavení doplňku VSTO.  
  
## <a name="register-vsto-add-ins-for-the-current-user-vs-all-users"></a>Zaregistrovat doplňků VSTO pro aktuálního uživatele oproti všichni uživatelé  
 Pokud doplňku VSTO je nainstalovaná, lze jej zaregistrovat dvěma způsoby:  
  
-   Pro aktuálního uživatele (to znamená, že je k dispozici pouze uživateli, který je přihlášený k počítači při instalaci doplňku VSTO). V takovém případě jsou položky registru vytvořil v rámci **HKEY_CURRENT_USER**.  
  
-   Pro všechny uživatele (každý uživatel, který se přihlásí k počítači, můžete použít doplněk VSTO). V takovém případě jsou položky registru vytvořil v rámci **HKEY_LOCAL_MACHINE**.  
  
 Všechny doplňků VSTO vytvořených pomocí sady Visual Studio lze zaregistrovat pro aktuálního uživatele. Však lze registrovat doplňků VSTO pro všechny uživatele jenom v určitých situacích. Tyto scénáře závisí na verzi aplikace Microsoft Office na počítači a způsobu nasazení doplňku VSTO.  
  
### <a name="microsoft-office-version"></a>Verze aplikace Microsoft Office  
 Aplikace Office může načíst doplňků VSTO registrované v části **HKEY_LOCAL_MACHINE** nebo **HKEY_CURRENT_USER**.  
  
 Načtení doplňků VSTO registrované v části **HKEY_LOCAL_MACHINE**, musí mít počítače balíček aktualizace 976477 nainstalována. Další informace najdete na webu [http://go.microsoft.com/fwlink/?LinkId=184923](http://go.microsoft.com/fwlink/?LinkId=184923).  
  
### <a name="deployment-type"></a>Typ nasazení  
 Pokud používáte ClickOnce k nasazení doplňku VSTO, doplňku VSTO se dají registrovat jenom pro aktuálního uživatele. Důvodem je, že ClickOnce podporuje pouze vytváření klíčů pod **HKEY_CURRENT_USER**. Pokud chcete zaregistrovat Add-in VSTO pro všechny uživatele v počítači, musíte použít instalační služby systému Windows k nasazení doplňku VSTO. Další informace o těchto typech nasazení najdete v tématu [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md) a [nasazení řešení Office s použitím Instalační služby systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
## <a name="registry-entries"></a>Položky registru  
 Požadované položky registru doplňku VSTO jsou umístěny ve složce následující klíč registru pro všechny aplikace s výjimkou aplikace Visio, kde *kořenové* je **HKEY_CURRENT_USER** nebo **HKEY_LOCAL_MACHINE** .  
  
 **Všechny aplikace s výjimkou aplikace Visio**  
  
|Verze systému Office|Cesta konfigurace|  
|--------------------|------------------------|  
|32bitová|*Kořenové*\Software\Microsoft\Office\\*název aplikace*\Addins\\*ID doplňku*|  
|64bitových|*Kořenové*\Software\Wow6432Node\Microsoft\Office\\*název aplikace*\Addins\\*ID doplňku*|  
  
 **Aplikace Visio**  
  
|Verze systému Office|Cesta konfigurace|  
|--------------------|------------------------|  
|32bitová|*Kořenové*\Software\Microsoft\Visio\Addins\\*ID doplňku*|  
|64bitových|*Kořenové*\Software\Wow6432Node\Visio\Addins\\*ID doplňku*|  
  
 Následující tabulka uvádí položky v tomto klíči registru.  
  
|Položka|Typ|Hodnota|  
|-----------|----------|-----------|  
|**Popis**|REG_SZ|Požadováno. Stručný popis doplňku VSTO.<br /><br /> Tento popis se zobrazí, když uživatel vybere doplněk VSTO v **doplňky** podokně **možnosti** dialogové okno v aplikaci Microsoft Office.|  
|**FriendlyName**|REG_SZ|Požadováno. Popisný název VSTO Add-in zobrazené v **COM Doplňky** dialogové okno v aplikaci Microsoft Office. Výchozí hodnota je ID VSTO Add-in.|  
|**LoadBehavior –**|REG_DWORD|Požadováno. Hodnota, která určuje, kdy se aplikace pokusí načíst doplňku VSTO a aktuální stav VSTO doplněk (načíst nebo odpojeno).<br /><br /> Tato položka je ve výchozím nastavení do 3, která určuje, že doplňku VSTO je načtena při spuštění. Další informace najdete v tématu [LoadBehavior – hodnoty](#LoadBehavior). **Poznámka:** Pokud uživatel zakáže doplňku VSTO, tato akce upraví **LoadBehavior** hodnotu **HKEY_CURRENT_USER** podregistru. Pro každého uživatele, hodnota **LoadBehavior** hodnota v podregistru HKEY_CURRENT_USER přepíše výchozí **LoadBehavior** definované v **HKEY_LOCAL_MACHINE** hive.|  
|**Manifest**|REG_SZ|Požadováno. Úplná cesta manifest nasazení pro doplňku VSTO. Cesta může být umístění v místním počítači, síťové sdílené složky (UNC) nebo na webovém serveru (HTTP).<br /><br /> Pokud použijete k nasazení řešení. Instalační služba systému Windows, musíte přidat předponu **file:///** k **manifest** cestu. Musíte také připojit řetězec  **&#124;vstolocal** (tedy znakem **&#124;** následuje **vstolocal**) na konec této cesty. Tím se zajistí, že vaše řešení je načtena z instalační složky, nikoli mezipaměti ClickOnce. Další informace najdete v tématu [nasazení řešení Office s použitím Instalační služby systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md). **Poznámka:** při sestavování doplňku VSTO ve vývojovém počítači Visual Studio automaticky připojí  **&#124;vstolocal** řetězec, který má tato položka registru.|  
  
###  <a name="OutlookEntries"></a> Položky registru pro oblastí formulářů aplikace Outlook  
 Pokud vytvoříte vlastní formulář oblast VSTO Add-in pro aplikaci Outlook, položky registru další slouží k registraci oblasti formuláře aplikace Outlook. Tyto položky jsou vytvářené v různých klíč pro každou zprávu třídu, která podporuje oblasti formuláře. Tyto klíče registru jsou v následujícím umístění, kde *kořenové* je **HKEY_CURRENT_USER** nebo **HKEY_LOCAL_MACHINE**.  
  
 *Kořenové*\Software\Microsoft\Office\Outlook\FormRegions\\*message – třída*  
  
 Jako další položky registru sdíleny všech doplňků VSTO, Visual Studio vytvoří formulář položky registru oblast na vývojovém počítači při sestavování projektu. Pokud používáte ClickOnce k nasazení vašeho doplňku VSTO, položky registru jsou automaticky vytvoří na počítači koncového uživatele. Pokud používáte k nasazení vašeho doplňku VSTO Instalační služby systému Windows, musíte nakonfigurovat InstallShield Limited Edition projektu pro vytvoření položky registru v počítači koncového uživatele.  
  
 Další informace o položkách registru oblasti formuláře najdete v tématu [zadejte umístění oblasti formuláře ve vlastním formuláři](http://msdn.microsoft.com/library/office/ff868998.aspx). Další informace o oblastí formulářů aplikace Outlook najdete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
##  <a name="LoadBehavior"></a> LoadBehavior – hodnoty  
 **LoadBehavior** položka v části *kořenové*\Software\Microsoft\Office\\*název aplikace*\Addins\\*doplňku ID* klíč obsahuje bitovou kombinaci hodnot, které určují chování běhu v doplňku VSTO. Nejnižší verze pořadí (hodnoty 0 a 1) určuje, zda doplňku VSTO je aktuálně odpojeno nebo načíst. Další bits signalizují, že se aplikace pokusí načíst doplňku VSTO.  
  
 Obvykle **LoadBehavior** položka má být nastavena na 0, 3 nebo 16 (v decimální): když doplňku VSTO je nainstalován na počítačích koncových uživatelů. Ve výchozím nastavení, Visual Studio nastaví **LoadBehavior** položku doplňku VSTO na 3 při vytvoření nebo při publikování.  
  
 Následující tabulka obsahuje seznam všech možných hodnot **LoadBehavior** položku. Některé popisy v této tabulce najdete načítání doplňku VSTO ručně nebo prostřednictvím kódu programu. Chcete-li ručně načíst doplňku VSTO, zaškrtněte políčko u doplňku VSTO v **doplňky modelu COM** dialogové okno v aplikaci. Chcete-li načíst doplňku VSTO prostřednictvím kódu programu, nastavte <xref:Microsoft.Office.Core.COMAddIn.Connect%2A> vlastnost <xref:Microsoft.Office.Core.COMAddIn> objekt, který reprezentuje doplňku VSTO pro **true**.  
  
|Hodnotu (decimální):|Stav doplňku VSTO|Chování zatížení doplňku VSTO|Popis|  
|--------------------------|-------------------------|--------------------------------|-----------------|  
|0|Není načten|Automatické načtení|Aplikace se nikdy pokusí automaticky načíst doplňku VSTO. Uživatele můžete zkusit ručně načíst doplňku VSTO nebo doplňku VSTO lze načíst prostřednictvím kódu programu.<br /><br /> Pokud doplňku VSTO úspěšně načtena, **LoadBehavior** hodnoty 0 zůstane, ale stav doplněk VSTO v **COM Doplňky** dialogové okno se aktualizuje na znamenat, že doplňku VSTO je načtena.|  
|1|Načten|Automatické načtení|Aplikace se nikdy pokusí automaticky načíst doplňku VSTO. Uživatele můžete zkusit ručně načíst doplňku VSTO nebo doplňku VSTO lze načíst prostřednictvím kódu programu.<br /><br /> I když **COM Doplňky** dialogové okno označuje, že doplňku VSTO je načtena po spuštění aplikace doplňku VSTO není načtený, dokud je načten ručně nebo prostřednictvím kódu programu.<br /><br /> Pokud aplikace úspěšně načte VSTO Add-in **LoadBehavior** hodnota změní na hodnotu 0 a zůstane v umístění 0 po zavření aplikace.|  
|2|Není načten|Načíst při spuštění|Aplikace nebude pokoušet automaticky načíst doplňku VSTO. Uživatele můžete zkusit ručně načíst doplňku VSTO nebo doplňku VSTO lze načíst prostřednictvím kódu programu.<br /><br /> Pokud aplikace úspěšně načte VSTO Add-in **LoadBehavior** hodnota změní na 3 a zůstane v 3 po zavření aplikace.|  
|3|Načten|Načíst při spuštění|Aplikace se pokusí načíst doplňku VSTO při spuštění aplikace. Toto je výchozí hodnota při vytvoření nebo publikování doplňku VSTO v sadě Visual Studio.<br /><br /> Pokud aplikace úspěšně načte VSTO Add-in **LoadBehavior** hodnota zůstane 3. Pokud dojde k chybě při načítání VSTO Add-in **LoadBehavior** hodnota změní na hodnotu 2 a zůstane na 2 po zavření aplikace.|  
|8|Není načten|Načítání na vyžádání|Aplikace nebude pokoušet automaticky načíst doplňku VSTO. Uživatele můžete zkusit ručně načíst doplňku VSTO nebo doplňku VSTO lze načíst prostřednictvím kódu programu.<br /><br /> Pokud aplikace úspěšně načte VSTO Add-in **LoadBehavior** hodnota změní na 9.|  
|9|Načten|Načítání na vyžádání|Doplňku VSTO budou načteny pouze v případě, že aplikace vyžaduje, například když uživatel klikne na element uživatelského rozhraní, která používá funkce VSTO Add-in (například vlastní tlačítka na pásu karet).<br /><br /> Pokud aplikace úspěšně načte VSTO Add-in **LoadBehavior** hodnota zůstane 9, ale stav doplněk VSTO v **doplňky modelu COM** dialogové okno se aktualizuje na znamenat, že doplňku VSTO nyní načíst. Pokud dojde k chybě při načítání VSTO Add-in **LoadBehavior** hodnota změní na 8.|  
|16|Načten|První doba načítání a zatížení na vyžádání|Nastavte tuto hodnotu, pokud chcete doplňku VSTO mají být načtena na vyžádání. Když uživatel spustí aplikaci prvním načtení aplikace doplňku VSTO. Při příštím uživatel spustí aplikaci, všechny prvky uživatelského rozhraní, které jsou definovány pomocí doplňku VSTO načtení aplikace, ale doplňku VSTO není načtený, dokud uživatel klikne na prvku uživatelského rozhraní, která souvisí s doplňku VSTO.<br /><br /> Až se aplikace úspěšně načte doplňku VSTO pro první **LoadBehavior** hodnotu zůstane 16, když je načten doplňku VSTO. Po zavření aplikace **LoadBehavior** hodnota změní na 9.|  
  
## <a name="see-also"></a>Viz také:  
 [Architektura řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Sestavení řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  