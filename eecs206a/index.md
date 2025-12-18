---
layout: default
title: EECS 206A Final Project
permalink: /eecs206a/
---

<link rel="stylesheet" href="{{ '/eecs206a/assets/css/style.css' | relative_url }}">

<div class="hero">
  <div class="hero-content">
    <h1 class="hero-title">EECS 206A Final Project</h1>
    <p class="hero-subtitle">Robotics - 3D Reconstruction with Robotic Manipulation</p>
    <p class="hero-description">A comprehensive robotics system combining manipulation, perception, and 3D reconstruction</p>
  </div>
</div>

<div class="container">
  <section class="overview">
    <h2>Project Overview</h2>
    <p>
      This project demonstrates an integrated robotics system that combines robotic manipulation, 
      computer vision, and 3D reconstruction. The system uses a UR7e robotic arm with a RealSense 
      camera to capture multi-view images of objects, which are then processed using COLMAP for 
      structure-from-motion and 3D Gaussian Splatting for high-quality 3D reconstruction.
    </p>
  </section>

  <section class="features">
    <h2>Key Features</h2>
    <div class="feature-grid">
      <div class="feature-card">
        <h3>🤖 Robotic Manipulation</h3>
        <p>Automated camera positioning using UR7e robotic arm with MoveIt motion planning</p>
      </div>
      <div class="feature-card">
        <h3>📷 Multi-View Capture</h3>
        <p>Systematic image acquisition using RealSense camera with pose tracking</p>
      </div>
      <div class="feature-card">
        <h3>🎯 ArUco Marker Detection</h3>
        <p>Precise pose estimation and coordinate frame alignment</p>
      </div>
      <div class="feature-card">
        <h3>🌐 3D Reconstruction</h3>
        <p>High-quality 3D scene reconstruction using COLMAP and Gaussian Splatting</p>
      </div>
    </div>
  </section>

  <section class="methodology">
    <h2>Methodology</h2>
    <div class="methodology-steps">
      <div class="step">
        <div class="step-number">1</div>
        <div class="step-content">
          <h3>Planning & Trajectory Generation</h3>
          <p>Generate optimal camera trajectories for comprehensive scene coverage using inverse kinematics and motion planning</p>
        </div>
      </div>
      <div class="step">
        <div class="step-number">2</div>
        <div class="step-content">
          <h3>Image Capture</h3>
          <p>Execute planned trajectories while capturing synchronized images and camera poses using ROS2</p>
        </div>
      </div>
      <div class="step">
        <div class="step-number">3</div>
        <div class="step-content">
          <h3>Structure from Motion</h3>
          <p>Process multi-view images with COLMAP to extract camera poses and sparse 3D point clouds</p>
        </div>
      </div>
      <div class="step">
        <div class="step-number">4</div>
        <div class="step-content">
          <h3>3D Gaussian Splatting</h3>
          <p>Train 3D Gaussian Splatting models for photorealistic novel view synthesis and dense reconstruction</p>
        </div>
      </div>
    </div>
  </section>

  <section class="results">
    <h2>Results</h2>
    <div class="results-gallery">
      <div class="result-item">
        <h3>Point Cloud Reconstruction</h3>
        <p>Dense point clouds extracted from multi-view images</p>
        <!-- Add your images here -->
        <!-- <img src="{{ '/eecs206a/images/pointcloud.png' | relative_url }}" alt="Point Cloud"> -->
      </div>
      <div class="result-item">
        <h3>3D Gaussian Splatting</h3>
        <p>High-quality rendered views from trained Gaussian Splatting model</p>
        <!-- Add your images/videos here -->
        <!-- <img src="{{ '/eecs206a/images/gaussian_splatting.png' | relative_url }}" alt="Gaussian Splatting"> -->
      </div>
      <div class="result-item">
        <h3>Trajectory Visualization</h3>
        <p>Planned and executed camera trajectories</p>
        <!-- Add your visualizations here -->
        <!-- <img src="{{ '/eecs206a/images/trajectory.png' | relative_url }}" alt="Trajectory"> -->
      </div>
    </div>
  </section>

  <section class="tech-stack">
    <h2>Technology Stack</h2>
    <div class="tech-list">
      <span class="tech-badge">ROS2</span>
      <span class="tech-badge">MoveIt</span>
      <span class="tech-badge">COLMAP</span>
      <span class="tech-badge">3D Gaussian Splatting</span>
      <span class="tech-badge">Python</span>
      <span class="tech-badge">OpenCV</span>
      <span class="tech-badge">RealSense</span>
      <span class="tech-badge">UR7e</span>
    </div>
  </section>

  <section class="links">
    <h2>Resources</h2>
    <div class="link-buttons">
      <a href="https://github.com/yaviddang20" class="btn btn-primary" target="_blank">GitHub Repository</a>
      <a href="/" class="btn btn-secondary">Back to Home</a>
    </div>
  </section>
</div>
