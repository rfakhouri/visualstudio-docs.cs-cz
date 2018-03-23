---
title: Vytvoření prostředí pro vývoj .NET Core s kontejnery pomocí Kubernetes v cloudu pomocí sady Visual Studio – krok 6 – Další informace o vývoj v týmu | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: ghogen
ms.openlocfilehash: fb05df7782c23c6caa973e0c1ad3e9433e8b2470
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Začínáme v připojeném prostředí s .NET Core a Visual Studio

Předchozí krok: [jiný kontejner](get-started-netcore-visualstudio-05.md)

## <a name="learn-about-team-development"></a>Další informace o vývoj v týmu

Naše aplikace kód jsme, pokud jste spustit jako v případě, že nám pouze vývojář pracující na aplikaci. V této části jsme dozvíte, jak připojené prostředí zjednodušuje vývoj v týmu:
* Povolte tým práci ve stejném prostředí vývoj vývojářům.
* Podporuje každý vývojář iterace na kód v izolaci a bez obav z nejnovější jiné.
* Testování kódu klient server, před potvrzení kódu bez nutnosti vytvoření mocks nebo simulovat závislosti.

## <a name="challenges-with-developing-microservices"></a>Problémy s vývojem mikroslužeb
Naše ukázková aplikace není v tuto chvíli velmi složité. Ale v vývoj skutečných problémů brzy vznikat víc služeb se přidávají a zvětšování vývojový tým.

Obrázek sami práce na službě, která komunikuje s spoustě dalších služeb.

1. Může stát vzhledem ke spuštění všechno místně pro vývoj. Vývojářském počítači nemusí mít dostatek prostředků ke spuštění celé aplikace. Nebo možná vaše aplikace obsahuje koncové body, které musí být veřejně přístupný (například aplikace reaguje na webhook, jehož z aplikace SaaS).
1. Můžete zkusit spustit pouze služby, které závisí na, ale to znamená, že by potřebovat znát Úplné uzavření závislosti (například závislosti závislosti). Nebo, bude stačit není snadno zjistit, jak sestavit a spustit závislostmi, protože nebyla pracovat s nimi.
1. Někteří vývojáři uchýlit k simulaci nebo mocking si řadu závislé služby. To může pomoct někdy, ale Správa těchto mocks může trvat brzy na svůj vlastní náročnost vývoje. Navíc to vede k prostředí dev vyhledávání příliš neliší do produkčního prostředí a jemně chyby můžete ovládat.
1. Z toho vyplývá, že to libovolného typu klient server testování bude obtížné. Testování integrace může dojít pouze reálně po potvrzení, což znamená, že jsme se zobrazit problémy, později v cyklu vývoje.

    ![](media/microservices-challenges.png)

## <a name="work-in-a-shared-development-environment"></a>Fungovaly v prostředí s sdílené vývoj
S prostředím připojen, můžete nastavit *sdílené* vývojového prostředí v Azure. Každý vývojář se můžou zaměřit na jejich součásti aplikace a můžete interaktivně vyvíjet *předem potvrdit kód* v prostředí, které již obsahuje všechny ostatní služby a cloudové prostředky, které jejich scénářů závisí na. Závislosti jsou vždy aktuální a vývojáři pracují způsobem, který odpovídá produkční.

## <a name="work-in-your-own-space"></a>Práce v vlastní místa
Když budete vyvíjet kódu služby a předtím, než jste připraveni zkontrolujte ho v kódu často nebudou ve funkčním stavu. Můžete se pořád interaktivně službu shaping, jeho otestováním a experimentování se řešení. Připojeném prostředí nabízí koncepci **místo**, který umožňuje pracovat v izolaci a bez obavy z nejnovější členové týmu.

Proveďte následující a ujistěte se, jak naše `webfrontend` a `mywebapi` služby spuštěné v našem vývojového prostředí **a v `mainline` místo**.
1. Zavřít všechny F5 nebo ladicí relace pro obě služby, ale nechat otevřené projektů v sadě Visual Studio windows.
2. Přejít do okna Visual Studio s `mywebapi` projektu a stiskněte klávesu Ctrl + F5 a spusťte službu bez připojit ladicí program
3. Přejít do okna Visual Studio s `webfrontend` projektu a stiskněte klávesu Ctrl + F5 a spusťte jej také.

> [!Note]
V některých případech je potřeba po ní, webová stránka se nejprve zobrazí následující Ctrl + F5 aktualizujte webový prohlížeč.

Každý, kdo otevře veřejnou adresu URL a přejde do webové aplikace se vyvolat kódová cesta jsme napsali které spustí prostřednictvím obě služby pomocí výchozího `mainline` místa. Nyní předpokládejme, že chcete pokračovat ve vývoji `mywebapi` – jak jsme to a není přerušení ostatní vývojáři, kteří používají vývojového prostředí? K tomu, nastavíme vlastní místa.

### <a name="create-a-new-space"></a>Vytvoření nového prostoru
V sadě Visual Studio můžete vytvořit další mezery, které se nepoužívá, pokud F5 nebo Ctrl + F5 služby. Můžete volat mezeru nic, co byste chtěli a může být flexibilní o tom, co je (např.) `sprint4` nebo `demo`).

Následujícím postupem vytvoření nového prostoru:
1. Přejít do okna Visual Studio s `mywebapi` projektu.
2. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **vlastnosti**.
3. Vyberte **ladění** karty na levé straně zobrazíte nastavení připojení prostředí.
4. Odsud můžete změnit nebo vytvořit připojení prostředí nebo místa, které se bude používat při F5 nebo Ctrl + F5. *Musí být vybrána připojené prostředí jste vytvořili dříve*.
5. V **místo** rozevíracího seznamu vyberte **< vytvořit nový prostor... >**.

    ![](images/Settings.png)

6. V **přidejte místo** dialogovém okně zadejte název pro místa a klikněte na tlačítko **OK**. Používal jsem náš název ("scott") pro nový prostor tak, aby se osobní Moje spolupracovníkům jaké místa v práci.

    ![](images/AddSpace.png)

7. Teď byste měli vidět vývojového prostředí a nový prostor vybrané na stránce vlastností projektu.

    ![](images/Settings2.png)

### <a name="update-code-for-mywebapi"></a>Aktualizujte kód pro *mywebapi*

1. V `mywebapi` projektu zkontrolujte kódu změňte `string Get(int id)` metoda v souboru `ValuesController.cs` následujícím způsobem:
 
    ```csharp
    [HttpGet("{id}")]
    public string Get(int id)
    {
        return "mywebapi now says something new";
    }
    ```

2. Nastavte zarážky v této aktualizované blok kódu (už můžete mít jeden z nastavit před).
3. Stiskněte F5 pro spuštění `mywebapi` služby. Tato akce spustí službu ve vašem vývojovém prostředí pomocí vybraného místa, což v mém případě je `scott`.

Zde je diagram, který vám pomůže pochopit, jak fungují jiné prostory. Modré cesty ukazuje žádosti o prostřednictvím `mainline` místa, což je výchozí cesta použít, pokud žádné místo se přidá jako předpona k adrese URL. Zelená cesta ukazuje žádosti o prostřednictvím `scott` místa.

![](media/Space-Routing.png)

Tato integrované funkce připojené prostředí umožňuje otestovat kód začátku do konce ve sdílené evironment bez nutnosti každý vývojář se znovu vytvořit úplné zásobníku služeb v jejich místo. Všimněte si, že tento směrování vyžaduje šíření hlavičky k přeposlání v kódu aplikace, jak je ukázáno v předchozím kroku tohoto průvodce.

## <a name="test-code-running-in-the-scott-space"></a>Testovací kód spuštěný ve `scott` místa
K otestování naší nové verze `mywebapi` ve spojení s `webfrontend`, otevřete prohlížeč na adresu URL bodu veřejný přístup `webfrontend` (např. https://webfrontend-teamenv.vsce.io) a přejděte na stránku o. Měli byste vidět na původní zprávu "Hello z webfrontend a Hello z mywebapi".

Nyní přidejte část "scott-" na adresu URL, přečte něco podobného jako https://scott-webfrontend-teamenv.vsce.io a aktualizujte stránku prohlížeče. Zarážek nastavené ve vaší `mywebapi` získat přístupů do projektu. Klikněte na tlačítko F5, aby bylo možné pokračovat a v prohlížeči se teď měla zobrazit novou zprávu "Hello z webfrontend a mywebapi teď uvádí nové". Důvodem je, že cesta k aktualizované kódu v `mywebapi` běží v `scott` místa.

> [!div class="nextstepaction"]
> [Shrnutí](get-started-netcore-visualstudio-07.md)