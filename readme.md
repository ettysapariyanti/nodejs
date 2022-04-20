# NodeJS

![image](https://user-images.githubusercontent.com/29531817/164135523-6eee5fee-39a0-4905-9134-dcb4b8cc7695.png)


source code yg berhasil berjalan untuk tarik data saham End Of Day untuk situs https://www.stockdata.org/ :

```nodejs

const https = require('https');

// gunakan url dari stock data

const url = 'https://api.stockdata.org/v1/data/eod?symbols=INDF.JK&api_token=BfaSyyLCiQbK27eZbaPWxEX5wX1yTtZXI0I4Ydlm';

const request = https.request(url, (response) => {

    let data = '';

    response.on('data', (chunk) => {

        data = data + chunk.toString();

    });

    response.on('end', () => {

        const body = JSON.parse(data);

        console.log(body);

    });

    
});


request.end()



```




