---
layout: default
title: EECS 206A Final Project
permalink: /eecs206a/
---

<link rel="stylesheet" href="{{ '/eecs206a/assets/css/style.css' | relative_url }}">

<div class="hero">
  <div class="hero-content">
    <h1 class="hero-title">EECS 206A Final Project</h1>
    <p class="hero-subtitle">Hand–Eye Calibrated 3D Gaussian Splatting with a Robot Arm</p>
    <p class="hero-description">
      Active perception and metric 3D reconstruction using robotic manipulation
    </p>
  </div>
</div>

<div class="container">

  <!-- ================= INTRODUCTION ================= -->

  <section class="overview">
    <h2>1. Introduction</h2>

    <h3>(a) Project Goal</h3>
    <p>
      The goal of this project is to build an autonomous 3D reconstruction system
      that integrates a robotic manipulator with hand–eye calibrated perception
      and 3D Gaussian Splatting. A camera rigidly mounted to a robot arm captures
      images from multiple viewpoints while executing planned motions. Using known
      robot kinematics and accurate hand–eye calibration, camera poses are expressed
      in a common world frame and used to reconstruct a high-fidelity 3D scene
      representation.
    </p>

    <h3>(b) Motivation and Challenges</h3>
    <p>
      This project is interesting because it combines robot kinematics, calibration,
      and modern neural scene representations into a single pipeline. Unlike
      traditional structure-from-motion approaches that estimate camera poses
      visually, this system leverages precise robot motion to provide metric,
      repeatable camera poses. Key challenges include accurate hand–eye calibration,
      synchronization between motion and image capture, and maintaining consistency
      between the robot coordinate frames and the learned 3D representation.
    </p>

    <h3>(c) Real-World Applications</h3>
    <p>
      The techniques developed in this project are applicable to robotic inspection,
      manipulation, and automation tasks. Potential applications include object-level
      scene understanding for grasp planning, robotic bin picking, industrial
      inspection, and building digital twins of workspaces for simulation and motion
      planning.
    </p>
  </section>

  <!-- ================= DESIGN ================= -->

  <section class="features">
    <h2>2. Design</h2>

    <h3>(a) Design Criteria</h3>
    <p>
      The system must produce accurate metric 3D reconstructions aligned to the
      robot base frame, support repeatable camera pose estimation using robot
      kinematics, and integrate with motion planning and control. Robustness to
      calibration error and sensor noise is also required.
    </p>

    <h3>(b) System Design</h3>
    <p>
      A fixed RGB camera is rigidly mounted to the robot end-effector. A hand–eye
      calibration procedure estimates the transformation between the camera and
      end-effector frames. The robot executes planned trajectories to sample views
      around the scene, and camera poses are computed using forward kinematics
      combined with the hand–eye transform. These poses are used directly in
      3D Gaussian Splatting.
    </p>

    <h3>(c) Design Choices and Trade-offs</h3>
    <p>
      Using robot-provided camera poses avoids drift and scale ambiguity but makes
      the system sensitive to calibration accuracy. 3D Gaussian Splatting was chosen
      over mesh- or voxel-based methods for its ability to represent fine geometry
      and appearance, at the cost of higher training complexity.
    </p>

    <h3>(d) Engineering Considerations</h3>
    <p>
      The reliance on robot kinematics improves repeatability and robustness in
      controlled environments. However, calibration errors directly affect
      reconstruction quality. The system prioritizes accuracy and consistency over
      computational efficiency, which is acceptable for offline reconstruction.
    </p>
  </section>

  <!-- ================= IMPLEMENTATION ================= -->

  <section class="methodology">
    <h2>3. Implementation</h2>

    <h3>(a) Hardware</h3>
    <p>
      The hardware setup consists of a UR7e robotic arm equipped with a rigidly
      mounted RealSense RGB camera. The camera mount ensures a fixed transformation
      between the camera and end-effector. The robot executes pre-planned
      trajectories to capture images from multiple viewpoints.
    </p>

    <h3>(b) Software and Components</h3>
    <p>
      ROS2 is used for robot control, motion planning, and data collection. MoveIt
      handles inverse kinematics and trajectory execution. OpenCV is used for
      calibration and image processing. The captured images and camera poses are
      processed using COLMAP and trained with a 3D Gaussian Splatting pipeline to
      produce the final reconstruction.
    </p>
  </section>

  <!-- ================= RESULTS ================= -->

  <section class="results">
    <h2>Results</h2>
    <div class="results-gallery">
      <div class="result-item">
        <h3>3D Reconstruction</h3>
        <p>
          The system successfully reconstructs dense 3D scenes with consistent
          geometry and appearance across viewpoints.
        </p>
      </div>
      <div class="result-item">
        <h3>Camera Trajectories</h3>
        <p>
          Planned and executed trajectories provide comprehensive scene coverage
          with accurate pose estimation.
        </p>
      </div>
    </div>
  </section>

  <!-- ================= TECH ================= -->

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
