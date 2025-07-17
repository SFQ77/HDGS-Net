<div style="background-color: #ffffff; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.08); padding: 30px; margin: 0 auto; max-width: 1200px;">

<!-- Title Section -->
<div style="background-color: #f8f9fa; border-radius: 8px; padding: 20px; margin-bottom: 30px; border-top: 4px solid #2c3e50;">
  <h1 align="center" style="font-family: 'Times New Roman', serif; font-size: 24pt; font-weight: bold; color: #2c3e50; margin: 0;">
    HDGS-Net: Single-Base Resolution Nucleosome Occupancy Prediction in <em>Saccharomyces cerevisiae</em> Genome
  </h1>
</div>

<!-- Subtitle & Divider -->
<p align="center" style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; margin: 0 0 20px 0; font-style: italic;">
  A comprehensive pipeline for nucleosome occupancy prediction using hybrid dilated gated separable convolutional neural networks
</p>
<hr style="border: 0; height: 1px; background-color: #e9ecef; margin: 30px 0;">

<!-- 1. Project Overview -->
<div style="margin-bottom: 40px;">
  <h2 style="font-family: 'Times New Roman', serif; font-size: 16pt; font-weight: bold; color: #1a5276; margin-top: 0; padding-bottom: 8px; border-bottom: 2px solid #e9ecef;">
    1. Project Overview
  </h2>
  <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.8; text-align: justify; margin-left: 10px;">
    The Hybrid Dilated Gated Separable Convolutional Neural Network (HDGS-Net) is a novel deep learning framework designed to predict nucleosome occupancy at single-base resolution across the entire genome of <em>Saccharomyces cerevisiae</em>. This repository provides complete code implementations and workflows to replicate the analysis, with demo data included for pipeline validation.
  </p>
</div>

<!-- 2. Demo Data Specifications -->
<div style="margin-bottom: 40px;">
  <h2 style="font-family: 'Times New Roman', serif; font-size: 16pt; font-weight: bold; color: #1a5276; margin-top: 0; padding-bottom: 8px; border-bottom: 2px solid #e9ecef;">
    2. Demo Data Specifications
  </h2>
  <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.8; text-align: justify; margin-left: 10px;">
    Due to large raw data volume and GitHub's file size constraints, demo data are provided for workflow demonstration:
  </p>
  <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.8; margin: 10px 0 10px 40px;">
    <li>1% random sample of genome-wide occupancy data</li>
    <li>5% random sample of TSS-TTS region data</li>
  </ul>
  
  <div style="background-color: #fff3cd; border-left: 4px solid #ffc107; padding: 12px; margin: 15px 10px; border-radius: 4px;">
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #856404; margin: 0; line-height: 1.6;">
      <strong>Note:</strong> Demo data illustrate pipeline integrity but may not reproduce the exact results in the original publication. All conclusions and final results are based on the peer-reviewed paper. Raw data are available in the supplementary materials of the paper; code for demo and raw data is identical.
    </p>
  </div>
</div>

<!-- 3. Key Guidelines for Usage -->
<div style="margin-bottom: 40px;">
  <h2 style="font-family: 'Times New Roman', serif; font-size: 16pt; font-weight: bold; color: #1a5276; margin-top: 0; padding-bottom: 8px; border-bottom: 2px solid #e9ecef;">
    3. Key Guidelines for Usage
  </h2>
  <div style="background-color: #f8f9fa; border-radius: 6px; padding: 15px; margin-left: 10px;">
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.8; margin: 0; padding-left: 20px;">
      <li><span style="font-weight: bold;">Step 0</span> is a conceptual overview (not executable).</li>
      <li>For demo data analysis, execute <span style="font-weight: bold;">Steps 1–26</span> sequentially.</li>
      <li>All code is interdependent: downstream scripts require outputs from upstream steps.</li>
      <li>Incomplete files (due to size limits) must be regenerated using provided scripts (see detailed workflows).</li>
    </ul>
  </div>
</div>

<!-- 4. Workflow Pipeline -->
<div style="margin-bottom: 40px;">
  <h2 style="font-family: 'Times New Roman', serif; font-size: 16pt; font-weight: bold; color: #1a5276; margin-top: 0; padding-bottom: 8px; border-bottom: 2px solid #e9ecef;">
    4. Workflow Pipeline
  </h2>

  <!-- Step 0 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      0. Global Overview (Conceptual Only)
    </h3>
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 15px; text-align: justify;">
      A high-level schematic of the entire analysis pipeline (for contextual understanding).
    </p>
  </div>

  <!-- Step 1 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      1. Genome Data Preparation
    </h3>
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 15px; text-align: justify;">
      1% demo occupancy data are sorted by chromosome number (descending) and stored in chromosome-specific files.
    </p>
  </div>

  <!-- Step 2 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      2. Threshold Determination & Visualization
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Calculate segmentation thresholds for each chromosome.</li>
      <li>Generate boxplots to visualize occupancy rate distributions across all chromosomes.</li>
    </ul>
  </div>

  <!-- Step 3 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      3. Training Site Selection
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Split chromosomes into <span style="font-style: italic;">high-occupancy</span> and <span style="font-style: italic;">normal-occupancy</span> groups using chromosome-specific thresholds.</li>
      <li>Downsample for balanced training:
        <ul style="margin: 5px 0 0 20px;">
          <li>High-occupancy: 1:3 ratio</li>
          <li>Normal-occupancy: 1:30 ratio</li>
        </ul>
      </li>
    </ul>
  </div>

  <!-- Step 4 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      4. DNA Sequence Extraction
    </h3>
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 15px; text-align: justify;">
      Extract 147 bp sequences (73 bp upstream/downstream of the center) from gap-free genome sequences, centered at training sites.
    </p>
  </div>

  <!-- Step 5 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      5. Feature & Label Encoding
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Convert 147 bp sequences to 16×146-dimensional sparse matrices via <span style="font-style: italic;">dinucleotide one-hot encoding</span> (saved as HDF5 files).</li>
      <li>Save corresponding occupancy rates as labels (HDF5 format).</li>
    </ul>
  </div>

  <!-- Step 6 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      6. HDGS-Net Training
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Train the custom HDGS-Net architecture on 16×146×1 features.</li>
      <li>Track absolute error during training.</li>
    </ul>
  </div>

  <!-- Step 7–8 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      7–8. Model Validation
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Validate HDGS-Net on training data for each chromosome.</li>
      <li>Compute <span style="font-style: italic;">Pearson Correlation Coefficient (PCC)</span> between predictions and true occupancy rates.</li>
    </ul>
  </div>

  <!-- Step 9–11 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      9–11. Model Testing
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Derive test sites by excluding training sites from raw data.</li>
      <li>Predict test data using the trained HDGS-Net.</li>
      <li>Compute PCC for test set performance.</li>
    </ul>
  </div>

  <!-- Step 12 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      12. Result Compilation
    </h3>
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 15px; text-align: justify;">
      Merge and sort training/test predictions with original <span style="font-style: italic;">dMean</span> values (for downstream visualization).
    </p>
  </div>

  <!-- Step 13 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      13. Nucleotide Preference Analysis
    </h3>
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 15px; text-align: justify;">
      Analyze mononucleotide/dinucleotide preferences in high- vs. low-occupancy groups (test sets).
    </p>
  </div>

  <!-- Step 14–16 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      14–16. Genome-Wide Clustering
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Convert nucleosome sequences to 16×146 one-hot matrices (with occupancy labels).</li>
      <li>Merge matrices into a single genome-wide digital matrix.</li>
      <li>Cluster into <span style="font-style: italic;">low/medium/high-occupancy groups</span> using K-Means.</li>
      <li>Visualize average dinucleotide frequency patterns as heatmaps.</li>
    </ul>
  </div>

  <!-- Step 17–18 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      17–18. TSS-TTS Data Processing
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Extract 147 bp sequences from TSS-TTS regions (1% sampled for demo).</li>
      <li>Convert TSS-TTS sequences to digital matrices.</li>
    </ul>
  </div>

  <!-- Step 19–22 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      19–22. SNFR/NNFR Classification
    </h3>
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 15px; text-align: justify;">
      Iteratively merge datasets (positive/negative strands, same/different positions) to address initial suboptimal classification. Train HDGS-Net on merged datasets for improved classification of SNFR/NNFR regions.
    </p>
  </div>

  <!-- Step 23–24 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      23–24. Heatmap Visualization
    </h3>
    <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 15px; text-align: justify;">
      Generate heatmaps for:
    </p>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 5px 0 0 45px; text-align: justify;">
      <li>Average digital matrices of NNFR/SNFR (stranded analysis).</li>
      <li>Average matrices across different genomic positions.</li>
    </ul>
  </div>

  <!-- Step 25–26 -->
  <div style="margin: 20px 0 25px 20px;">
    <h3 style="font-family: 'Times New Roman', serif; font-size: 14pt; font-weight: bold; color: #2980b9; margin: 0;">
      25–26. Model Comparison
    </h3>
    <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 30px; text-align: justify;">
      <li>Bar charts comparing PCC of 4 models across 16 chromosomes.</li>
      <li>Performance comparison (MSE and PCC) between HDGS-Net and traditional ML regression models (chromosome I data), visualized with bar charts.</li>
    </ul>
  </div>
</div>

<!-- Critical Notes -->
<div style="margin-bottom: 40px; background-color: #fff5f5; border-radius: 6px; padding: 20px; border-left: 4px solid #e74c3c;">
  <h2 style="font-family: 'Times New Roman', serif; font-size: 16pt; font-weight: bold; color: #c0392b; margin-top: 0;">
    Critical Notes
  </h2>
  <ul style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.8; margin: 10px 0 0 30px; text-align: justify;">
    <li>Execute steps sequentially: downstream code depends on upstream outputs.</li>
    <li>Raw data are available in the original publication (see Citation).</li>
    <li>Demo results are illustrative; refer to the paper for definitive conclusions.</li>
  </ul>
</div>

<!-- Contact -->
<div style="margin-bottom: 30px;">
  <h2 style="font-family: 'Times New Roman', serif; font-size: 16pt; font-weight: bold; color: #1a5276; margin-top: 0; padding-bottom: 8px; border-bottom: 2px solid #e9ecef;">
    Contact
  </h2>
  <p style="font-family: 'Times New Roman', serif; font-size: 12pt; color: #34495e; line-height: 1.6; margin: 8px 0 0 10px;">
    For questions or issues, contact the repository maintainer.
  </p>
</div>

<!-- Footer -->
<hr style="border: 0; height: 1px; background-color: #e9ecef; margin: 30px 0;">
<p align="center" style="font-family: 'Times New Roman', serif; font-size: 10pt; color: #7f8c8d; margin: 0;">
</p>

</div>
