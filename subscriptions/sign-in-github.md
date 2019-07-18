---
title: Přihlášení k předplatným sady Visual Studio s vaším účtem GitHubu | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/11/2019
ms.topic: conceptual
description: Přečtěte si, jak se přihlásit k předplatným sady Visual Studio s vaším účtem GitHub.
ms.openlocfilehash: 6279c9399a42bc07579f48c887987b4b662da9da
ms.sourcegitcommit: 57866dd72fd0e15ce61128df70729b427a2d02eb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2019
ms.locfileid: "68315595"
---
# <a name="signing-in-to-visual-studio-subscriptions-with-your-github-account"></a>Přihlášení k předplatným sady Visual Studio s vaším účtem GitHubu 

Postup přihlášení k předplatnému sady Visual Studio závisí na typu účtu, který používáte. Můžete například použít účet Microsoft (MSA) nebo e-mailovou adresu poskytnutou zaměstnavatelem nebo školou. Od ledna 2019 teď můžete k přihlášení k některým předplatným použít taky svůj účet GitHub. 

Tento článek obsahuje kroky pro přihlášení k vašemu účtu GitHub.

## <a name="signing-in-with-your-github-account"></a>Přihlášení pomocí účtu GitHub

Podpora identit na GitHubu umožňuje používat váš stávající účet GitHub jako přihlašovací údaje pro nové nebo existující účet Microsoft, propojuje svůj účet GitHub s vaším účet Microsoft. 

Když se přihlásíte pomocí GitHubu, Microsoft zkontroluje, jestli se některé e-mailové adresy přidružené k vašemu účtu GitHubu shodují s existujícím osobním nebo podnikovým účet Microsoft. Pokud se adresa shoduje s vaším podnikovým účtem, zobrazí se místo toho výzva k přihlášení k tomuto účtu. Pokud se adresa shoduje s osobním účtem, přidáme váš účet GitHub jako metodu přihlašování k tomuto osobnímu účtu.

Po propojení GitHubu a účet Microsoft přihlašovacích údajů, můžete použít toto jednotné přihlašování kdekoli osobní účet Microsoft můžete použít, jako na webech Azure, aplikacích Office a Xbox. Tyto účty se taky dají použít k Azure Active Directory přihlášení hostů jako účet Microsoft, za předpokladu, že se e-mailová adresa shoduje s touto adresou na pozvánce.

> [!NOTE]
> Propojení identity GitHubu s účet Microsoft nedává Microsoftu přístup k kódu. Když aplikace, jako je například Azure DevOps a Visual Studio, vyžadují přístup k vašim úložištím kódu, budete vyzváni k udělení konkrétního souhlasu pro tento přístup. 

### <a name="frequently-asked-questions"></a>Nejčastější dotazy
Následující nejčastější dotazy vám pomohou v souvislosti s používáním přihlašovacích údajů účtu GitHub pro přihlášení k předplatným sady Visual Studio.

#### <a name="q-i-forgot-my-github-password--how-can-i-access-my-account-now"></a>Č Zapomněl (a) jsem svoje heslo GitHubu.  Jak mám teď přístup k mému účtu?
O:  Svůj účet GitHubu můžete obnovit tak, že budete pokračovat v [resetování hesla](https://github.com/password_reset). Nebo můžete obnovit účet Microsoft propojených na GitHubu zadáním e-mailové adresy účtu GitHubu na adrese [obnovení účtu](https://account.live.com/password/reset).

#### <a name="q-i-deleted-my-github-account--how-can-i-access-my-microsoft-account-msa-now"></a>Č Odstranil (a) jsem svůj účet GitHubu.  Jak mám přístup k účet Microsoft (MSA) nyní?
O: Pokud nemáte žádné jiné přihlašovací údaje v MSA (třeba heslo, ověřovací aplikace nebo bezpečnostní klíč), můžete obnovit účet Microsoft pomocí e-mailové adresy, kterou jste k němu připojeni. Začněte tím, že přejdete na [Obnovit účet](https://account.live.com/password/reset). Budete muset přidat heslo k vašemu účtu, abychom vám věděli, jak vás přihlašovat později. 

#### <a name="q-theres-no-sign-in-with-github-option-on-the-sign-in-page--how-can-i-use-my-github-credentials-to-sign-in"></a>Č Na přihlašovací stránce není možnost přihlásit se pomocí GitHubu.  Jak se dá použít přihlašovací údaje GitHubu pro přihlášení?
O:  Zadejte e-mailovou adresu účtu GitHub, kterou jste si zvolili při vytváření účet Microsoft propojených na GitHubu. Podíváme se na GitHub a pošleme vám přihlašovací vše. Nebo, pokud máte na přihlašovací stránce odkaz Možnosti přihlášení, použijte tlačítko **Přihlásit se pomocí GitHubu** , které se zobrazí po kliknutí na tento odkaz. 

#### <a name="q-i-cant-sign-in-to-some-of-my-apps-and-products-with-github--why"></a>Č Nemůžu se přihlásit k některým z mých aplikací a produktů pomocí GitHubu.  Proč?
O:  Ne všechny produkty Microsoftu mají přístup k GitHub.com ze své přihlašovací stránky, například konzol Xbox. Když zadáte e-mailovou adresu z propojeného účtu GitHubu, pošleme na tuto adresu kód, abychom mohli ověřit, že je to opravdu. Pořád se přihlašujete ke stejnému účtu, a to jenom pomocí jiné metody přihlašování. 

#### <a name="q--ive-added-a-password-to-the-microsoft-account-i-have-linked-to-my-github-account--will-that-cause-a-problem"></a>Č  Přidal (a) jsem heslo k účet Microsoft připojenému k účtu GitHub.  Bude to způsobovat problém?
O:  Není zač. Tím se nezmění vaše heslo GitHubu. budete mít jenom jiný způsob, jak se přihlásit k vašemu účet Microsoft. Kdykoli se přihlásíte pomocí své e-mailové adresy, nabídneme vám možnost přihlašování s vaším účet Microsoft heslem nebo se budete muset přihlásit k GitHubu. Důrazně doporučujeme, abyste v případě potřeby přidání hesla měli jistotu, že se liší od hesla k vašemu účtu GitHub.

#### <a name="q-i-want-to-add-the-authenticator-app-to-the-account-i-created-using-github--can-i-do-that"></a>Č Chci přidat ověřovací aplikaci k účtu, který jste vytvořili pomocí GitHubu.  Mohu to udělat?
O:  Bez potíží – stačí stáhnout aplikaci a přihlásit se pomocí své e-mailové adresy. Když se přihlásíte pomocí své e-mailové adresy, zobrazí se výzva, abyste jako přihlašovací údaje zvolili [aplikaci ověřovatele](https://go.microsoft.com/fwlink/?linkid=2090219) nebo GitHub.

#### <a name="q-ive-enabled-two-factor-authentication-on-both-my-github-and-microsoft-accounts-msa-but-when-i-sign-in-to-my-msa-im-still-asked-to-authenticate-twice--why"></a>Č Povolili jsme dvojúrovňové ověřování na svém účtu GitHub i na účtu Microsoft (MSA), ale když se přihlásím k MSA, pořád se zobrazí výzva k ověření dvakrát.  Proč?
O: Z důvodu omezení zabezpečení počítá společnost Microsoft přihlašování pomocí GitHubu jako jednorázové ověření, a to i v případě, že je zde povoleno dvoustupňové ověřování. Proto bude nutné znovu provést ověření pro účet Microsoft. 

#### <a name="q--how-can-i-tell-if-my-microsoft-account-and-github-accounts-are-linked"></a>Č  Jak poznám, jestli jsou účty účet Microsoft a GitHubu propojené?
O:  Kdykoli se přihlásíte pomocí aliasu účtu (e-mailová adresa, telefonní číslo, jméno Skypu), zobrazí se vám všechny metody přihlášení pro váš účet. Pokud tam GitHub nevidíte, zatím jste ho nenastavili.

#### <a name="q--how-can-i-unlink-my-microsoft-and-github-accounts"></a>Č  Jak můžu zrušit propojení s účty Microsoft a GitHub? 
O:  Přejděte na [kartu zabezpečení](https://account.microsoft.com/security) Account.Microsoft.com a kliknutím na **Další možnosti zabezpečení** odpojte svůj účet GitHub. Zrušení propojení účtu GitHub ho odebere jako metodu přihlašování a odebere přístup k jakýmkoli úložištím GitHubu v aplikaci Visual Studio. Ostatní produkty Microsoftu si můžou požádat o přístup k vašemu účtu GitHubu samostatně, takže odebrání přístupu tady nebude odebírat přístup ve všech produktech. Na stránce [oprávnění aplikace](https://github.com/settings/applications) v profilu GitHubu můžete odvolat souhlas z aplikací, které jsou tady uvedené.

#### <a name="q--i-try-to-use-my-github-account-to-sign-in-but-im-prompted-that-i-already-have-a-microsoft-identity-that-i-should-use-instead--whats-happening"></a>Č  Zkusím použít svůj účet GitHub pro přihlášení, ale zobrazí se výzva, že již mám identitu Microsoftu, kterou mám použít místo toho.  Co se děje?
O:  Pokud máte na svém účtu GitHub Azure Active Directory e-mailovou adresu, znamená to, že už máte identitu Microsoftu, která má přístup k Azure a spouštět kanály CI pomocí vašeho kódu GitHubu. Pomocí tohoto účtu zajistíte, aby vaše prostředky a kanály pro vytváření prostředků Azure zůstaly v rámci svých organizačních hranic. Pokud ale provádíte osobní práci, doporučujeme, abyste na svém účtu GitHub umístili osobní e-mailovou adresu, abyste k nim měli vždycky přístup. Až to uděláte, zkuste se znovu přihlásit a při zobrazení výzvy k přihlášení ke svému pracovnímu nebo školnímu účtu vyberte **použít jinou e-mailovou adresu** . To vám umožní vytvořit novou účet Microsoft pomocí této osobní e-mailové adresy.

## <a name="next-steps"></a>Další postup
Po úspěšném přihlášení k portálu předplatných doporučujeme navštívit stránku https://my.visualstudio.com/benefits s výhodami a prozkoumat skvělé nástroje, služby a nabídky, které máte k dispozici.  