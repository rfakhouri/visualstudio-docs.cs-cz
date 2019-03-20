---
title: 'CA3147: Označte obslužné rutiny příkazů pomocí ValidateAntiForgeryToken'
ms.date: 08/08/2018
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 0cd54f932a99ea79bf792ebe4175ddc6a031ddcb
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2019
ms.locfileid: "58194441"
---
# <a name="ca3147-mark-verb-handlers-with-validateantiforgerytoken"></a>CA3147: Označte obslužné rutiny příkazů pomocí ValidateAntiForgeryToken

|||
|-|-|
|TypeName|MarkVerbHandlersWithValidateAntiForgeryToken|
|CheckId|CA3147|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina

Metody akce kontroleru ASP.NET MVC není označen atributem [ValidateAntiForgeryTokenAttribute](/previous-versions/aspnet/dd492108(v=vs.118)), nebo atribut určení příkaz protokolu HTTP, jako například [HttpGetAttribute](/previous-versions/aspnet/ee470993(v%3dvs.118)) nebo [ AcceptVerbsAttribute](/previous-versions/aspnet/dd470553%28v%3dvs.118%29).

## <a name="rule-description"></a>Popis pravidla

Při navrhování kontroler ASP.NET MVC, dávejte útoků proti padělání žádosti více webů. Útok proti padělání žádosti více webů odesílat škodlivé žádosti od ověřeného uživatele do vaší kontroler ASP.NET MVC. Další informace najdete v tématu [prevence XSRF/CSRF v ASP.NET MVC a na webových stránkách](/aspnet/mvc/overview/security/xsrfcsrf-prevention-in-aspnet-mvc-and-web-pages).

Toto pravidlo kontroluje, že kontroler ASP.NET MVC metod akce buď:

- Máte [ValidateAntiforgeryTokenAttribute](/previous-versions/aspnet/dd492108%28v%3dvs.118%29) a určení povolených příkazů HTTP, bez zahrnutí HTTP GET.

- Zadejte GET protokolu HTTP jako povolených operací.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Pro akce kontroleru ASP.NET MVC, které zpracovávají požadavky HTTP GET a nemají potenciálně škodlivé vedlejší účinky, přidejte [HttpGetAttribute](/previous-versions/aspnet/ee470993%28v%3dvs.118%29) metody.

   Pokud máte ASP.NET MVC požaduje akce kontroleru, který zpracovává HTTP GET a má potenciálně škodlivé vedlejší účinky, jako je třeba změna citlivá data, aplikace je ohrožen útoky proti padělání žádosti více webů.  Bude potřeba změnit návrh aplikace tak, aby pouze žádosti HTTP POST, PUT a DELETE provádět citlivé operace.

- Pro akce kontroleru ASP.NET MVC, které zpracovávají HTTP POST, PUT nebo požádá o odstranění, přidání [ValidateAntiForgeryTokenAttribute](/previous-versions/aspnet/dd492108(v=vs.118)) a atributů určujících povolené příkazy HTTP ([AcceptVerbsAttribute](/previous-versions/aspnet/dd470553%28v%3dvs.118%29) [HttpPostAttribute](/previous-versions/aspnet/ee264023%28v%3dvs.118%29), [HttpPutAttribute](/previous-versions/aspnet/ee470909%28v%3dvs.118%29), nebo [HttpDeleteAttribute](/previous-versions/aspnet/ee470917%28v%3dvs.118%29)). Kromě toho je třeba volat [HtmlHelper.AntiForgeryToken()](/previous-versions/aspnet/dd504812%28v%3dvs.118%29) metoda ze zobrazení MVC nebo Razor webové stránky. Příklad najdete v tématu [zkoumání metod edit a zobrazení upravit](/aspnet/mvc/overview/getting-started/introduction/examining-the-edit-methods-and-edit-view).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, pokud:

- Akce řadiče ASP.NET MVC nemá žádné škodlivé vedlejší účinky.

- Aplikace ověří daný token antiforgery jiným způsobem.

## <a name="validateantiforgerytoken-attribute-example"></a>Příklad ValidateAntiForgeryToken atribut

### <a name="violation"></a>Porušení

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            // You don't want an attacker to specify to who and how much money to transfer.

            return null;
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpPost]
        [ValidateAntiForgeryToken]
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            return null;
        }
    }
}
```

## <a name="httpget-attribute-example"></a>Příklad třídy MetadataExchangeClientMode atribut

### <a name="violation"></a>Porušení

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult Help(int topicId)
        {
            // This Help method is an example of a read-only operation with no harmful side effects.
            return null;
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpGet]
        public ActionResult Help(int topicId)
        {
            return null;
        }
    }
}
```
