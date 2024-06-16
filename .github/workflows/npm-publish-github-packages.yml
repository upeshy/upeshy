const express = require('express');
const bodyParser = require('body-parser');
const app = express();
const port = 3000;

app.use(bodyParser.json());

let latestPaymentData = {}; // Store the latest payment data

app.post('/webhook', (req, res) => {
    console.log('Webhook received:', req.body);
    latestPaymentData = {
        paymentId: req.body.payload.payment.entity.id,
        amount: req.body.payload.payment.entity.amount,
    };
    res.sendStatus(200);
});

app.get('/latestPayment', (req, res) => {
    res.json(latestPaymentData);
});

app.listen(port, () => {
    console.log(`Server listening at http://localhost:${port}`);
});
