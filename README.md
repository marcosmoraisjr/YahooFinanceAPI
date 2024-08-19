# YahooFinanceAPI
Biblioteca cliente C# para a API do Yahoo Finance.

# Biblioteca Cliente da API do Yahoo Finance

Biblioteca Cliente C# usada para interagir com a API do Yahoo Finance

[![Status de Build do yahoofinanceapi MyGet](https://www.myget.org/BuildSource/Badge/yahoofinanceapi?identifier=38997d9d-f6c0-4fd6-8f10-caa8cc0eb323)](https://www.myget.org/)

<h1>Como Instalar</h1>

`PM> Install-Package YahooFinanceClient`

<h1>O que é Fornecido?</h1>

Esta biblioteca oferece alguns métodos que facilitam a comunicação com a API do Yahoo Finance

| Dados de Preços                | Dados de Dividendos  | Dados de Volume       | Dados Médios           | Dados de Razão                        |
|--------------------------------|----------------------|-----------------------|------------------------|---------------------------------------|
| Ask                            | Dividend Yield       | Volume                | Day Low                | Earnings per Share                    |
| Bid                            | Dividend per Share   | Ask Size              | Day High               | EPS Estimate Current Year             |
| Ask Realtime                   | Dividend Pay Date    | Bid Size              | Last Trade Price       | EPS Estimate Next Year                |
| Bid Realtime                   | Ex-Dividend Date     | Last Trade Size       | 50 Day Moving Average  | EPS Estimate Next Quarter             |
| Previous Close                 |                      | Average Daily Volume  | 200 Day Moving Average | Book Value                            |
| Open                           |                      |                       | One Year Target Price  | EBITDA                                |
| 52 Week High                   |                      |                       |                        | Price / Sales                         |
| 52 Week Low                    |                      |                       |                        | Price / Book                          |
| 52 Week Low Change             |                      |                       |                        | P/E Ratio                             |
| 52 Week High Change            |                      |                       |                        | P/E Ratio (Realtime)                  |
| 52 Week Low Change (Percent)   |                      |                       |                        | PEG Ratio                             |
| 52 Week High Change (Percent)  |                      |                       |                        | Price / EPS Estimate Current Year     |
| 52 Week Range                  |                      |                       |                        | Price / EPS Estimate Next Year        |
|                                |                      |                       |                        | Short Ratio                           |

<h1>Exemplos</h1>

```csharp
var yf = new yf.YahooFinance();
var ativo = yahooFinanceClient.RetrieveStock("BBSA3.SA");

Console.WriteLine($"Preço Ask é {ativo.PricingData.Ask}");
Console.WriteLine($"Preço Bid é {ativo.PricingData.Bid}");
Console.WriteLine($"Preço de Abertura é {ativo.PricingData.Open}");
Console.WriteLine($"Preço de Fechamento Anterior é {ativo.PricingData.PreviousClose}");
```

```csharp
var yf = new yf.YahooFinance();
var ativo = yahooFinanceClient.RetrieveStock("PETR4.SA");

Console.WriteLine($"Volume é {ativo.VolumeData.CurrentVolume}");
Console.WriteLine($"Tamanho do Ask é {ativo.VolumeData.AskSize}");
Console.WriteLine($"Tamanho do Bid é {ativo.VolumeData.BidSize}");
Console.WriteLine($"Tamanho da Última Negociação é {ativo.VolumeData.LastTradeSize}");
Console.WriteLine($"Volume Diário Médio é {ativo.VolumeData.AverageDailyVolume}");
```
