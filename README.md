// server.js
import express from "express";
import cors from "cors";

const app = express();
app.use(cors());
app.use(express.json());

app.get("/", (req, res) => {
  res.send("Addy Proxy is running ✅");
});

app.post("/api", async (req, res) => {
  res.json({ success: true, message: "Proxy connected!" });
});

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => console.log(`✅ Server live on port ${PORT}`));
