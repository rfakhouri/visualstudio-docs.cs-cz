---
title: "Ukázkový projekt testů jednotek v sadě Visual Studio | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9edfd00b50442f03cda7d99fba87af6fb66ba5b7
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="sample-project-for-creating-unit-tests"></a>Ukázkový projekt testů jednotek

Tento ukázkový kód je určen pro použití v následující kurzy:

- [Návod: Vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). Tento názorný postup vás provede kroky pro vytváření a přizpůsobení testování částí, jejich spuštění a podívejte se na výsledky testu.

- [Návod: Použití nástroje testů z příkazového řádku](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). V tomto návodu můžete pomocí nástroje příkazového řádku MSTest.exe spouštět testy a zobrazit výsledky.

## <a name="sample-code"></a>Ukázkový kód

Pouze touto úmyslnou chybou v této ukázce je, že metodu v debetní "m_balance += částka" by měl mít minus, není plus přihlášení před symbolem rovná se.

```csharp
using System;

namespace BankAccountNS
{
    /// <summary>
    /// Bank Account demo class.
    /// </summary>
    public class BankAccount
    {
        private string m_customerName;

        private double m_balance;

        private bool m_frozen = false;

        private BankAccount()
        {
        }

        public BankAccount(string customerName, double balance)
        {
            m_customerName = customerName;
            m_balance = balance;
        }

        public string CustomerName
        {
            get { return m_customerName; }
        }

        public double Balance
        {
            get { return m_balance; }
        }

        public void Debit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount > m_balance)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount; // intentionally incorrect code
        }

        public void Credit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount;
        }

        private void FreezeAccount()
        {
            m_frozen = true;
        }

        private void UnfreezeAccount()
        {
            m_frozen = false;
        }

        public static void Main()
        {
            BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);

            ba.Credit(5.77);
            ba.Debit(11.22);
            Console.WriteLine("Current balance is ${0}", ba.Balance);
        }
    }
}
```

/ * Společností, organizací, produktů, názvů domén, e-mailové adresy, loga, osoby, místa a události použité v ukázkách jsou smyšlené. Žádné spojení se skutečnou společností, organizace, produktu, název domény, e-mailovou adresu, logem, osoba, místech nebo události je určený nebo událostmi. \*/

## <a name="working-with-the-code"></a>Práce s kódem

Pro práci s tímto kódem, musíte nejprve vytvořit projekt pro něj v sadě Visual Studio. Postupujte podle kroků v části "Příprava návodu" [návod: vytváření a spuštěné testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md).

## <a name="see-also"></a>Viz také

- [Návod: Vytváření a spouštění testů částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)
- [Návod: použití nástroje testů z příkazového řádku](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
