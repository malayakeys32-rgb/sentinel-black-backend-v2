import express from "express";
import cors from "cors";
import casesRoutes from "./src/routes/cases.js";
import operationsRoutes from "./src/routes/operations.js";
import evidenceRoutes from "./src/routes/evidence.js";
import timelineRoutes from "./src/routes/timeline.js";
import auditRoutes from "./src/routes/audit.js";

const app = express();
app.use(cors());
app.use(express.json());

// Routes
app.use("/cases", casesRoutes);
app.use("/operations", operationsRoutes);
app.use("/evidence", evidenceRoutes);
app.use("/timeline", timelineRoutes);
app.use("/audit", auditRoutes);

const PORT = process.env.PORT || 10000;
app.listen(PORT, () => {
  console.log(`Sentinel-Black backend running on port ${PORT}`);
});
