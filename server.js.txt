const express = require("express");
const app = express();
const connectDB = require("./config/connectDB");
const blogRoute = require("./routes/blog");



require('dotenv').config()
app.use(express.json()); 
const port = process.env.PORT;
connectDB();
app.use("/api/blog", blogRoute);
app.listen(port,()=>console.log("DONE"));