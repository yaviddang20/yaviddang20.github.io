---
layout: default
title: EECS 206A Final Project
permalink: /eecs206a/
---

<link rel="stylesheet" href="{{ '/eecs206a/assets/css/style.css' | relative_url }}">

<div class="hero">
  <div class="hero-content">
    <h1 class="hero-title">EECS 206A Final Project</h1>
    <p class="hero-subtitle">Robotics – 3D Reconstruction with Robotic Manipulation</p>
    <p class="hero-description">
      A robotics system combining hand–eye calibration, active perception,
      and 3D Gaussian Splatting
    </p>
  </div>
</div>

<div class="container">

  <section class="overview">
    <h2>Project Overview</h2>
    <p>
      This project presents an integrated robotics perception pipeline that combines
      a robotic manipulator with precise hand–eye calibration and modern neural
      scene representations. A UR7e robotic arm equipped with a RealSense camera
      autonomously captures multi-view images of a scene. Using known robot kinematics
      and calibrated camera poses, the images are fused into a global frame and
      reconstructed using 3D Gaussian Splatting.
    </p>
  </section>

  <section class="features">
    <h2>Key Features</h2>
    <div class="feature-grid">
      <div class="feature-card">
        <h3>Robotic Manipulation</h3>
        <p>
          Automated camera motion using a UR7e robotic arm with
          inverse kinematics and MoveIt-based motion planning
        </p>
      </div>
      <div class="feature-card">
        <h3>Multi-View Capture</h3>
        <p>
          Systematic image acquisition with synchronized camera poses
          obtained from robot forward kinematics
        </p>
      </div>
      <div class="feature-card">
        <h3>Hand–Eye Calibration</h3>
        <p>
          Accurate alignment between camera and robot frames enabling
          metric, repeatable reconstructions
        </p>
      </div>
      <div class="feature-card">
        <h3>3D Gaussian Splatting</h3>
        <p>
          High-fidelity 3D scene reconstruction and novel view synthesis
          using Gaussian Splatting
        </p>
      </div>
    </div>
  </section>

  <section class="methodology">
    <h2>Methodology</h2>
    <div class="methodology-steps">

      <div class="step">
        <div class="step-number">1</div>
        <div class="step-content">
          <h3>Trajectory Planning</h3>
          <p>
            Camera viewpoints are planned around the target scene using
            inverse kinematics and collision-aware motion planning.
          </p>
        </div>
      </div>

      <div class="step">
        <div class="step-number">2</div>
        <div class="step-content">
          <h3>Data Collection</h3>
          <p>
            The robot executes planned trajectories while capturing RGB images
            and recording precise camera poses via hand–eye calibration.
          </p>
        </div>
      </div>

      <div class="step">
        <div class="step-number">3</div>
        <div class="step-content">
          <h3>Pose Processing</h3>
          <p>
            Camera poses are expressed in a common world frame using robot
            forward kinematics and the calibrated camera–end-effector transform.
          </p>
        </div>
      </div>

      <div class="step">
        <div class="step-number">4</div>
        <div class="step-content">
          <h3>3D Gaussian Splatting</h3>
          <p>
            The captured images and known camera poses are used to train
            a 3D Gaussian Splatting model for dense reconstruction and
            photorealistic rendering.
          </p>
        </div>
      </div>

    </div>
  </section>

  <section class="results">
    <h2>Results</h2>
    <div class="results-gallery">
      <div class="result-item">
        <h3>Point Cloud Reconstruction</h3>
        <p>Dense point clouds generated from multi-view captures</p>
        <!-- <img src="{{ '/eecs206a/images/pointcloud.png' | relative_url }}" alt="Point Cloud"> -->
      </div>
      <div class="result-item">
        <h3>3D Gaussian Splatting</h3>
        <p>Photorealistic novel views rendered from the trained model</p>
        <!-- <img src="{{ '/eecs206a/images/gaussian.png' | relative_url }}" alt="Gaussian Splatting"> -->
      </div>
      <div class="result-item">
        <h3>Camera Trajectories</h3>
        <p>Planned and executed camera paths around the scene</p>
        <!-- <img src="{{ '/eecs206a/images/trajectory.png' | relative_url }}" alt="Trajectory"> -->
      </div>
    </div>
  </section>

  <section class="tech-stack">
    <h2>Technology Stack</h2>
    <div class="tech-list">
      <span class="tech-badge">ROS2</span>
      <span class="tech-badge">MoveIt</span>
      <span class="tech-badge">UR7e</span>
      <span class="tech-badge">RealSense</span>
      <span class="tech-badge">OpenCV</span>
      <span class="tech-badge">COLMAP</span>
      <span class="tech-badge">3D Gaussian Splatting</span>
      <span class="tech-badge">Python</span>
    </div>
  </section>

  <section class="links">
    <h2>Resources</h2>
    <div class="link-buttons">
      <a href="https://github.com/yaviddang20" class="btn btn-primary" target="_blank">
        GitHub Repository
      </a>
      <a href="/" class="btn btn-secondary">Back to Home</a>
    </div>
  </section>

</div>
