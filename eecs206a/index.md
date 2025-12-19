---
layout: default
title: EECS 206A Final Project
permalink: /eecs206a/
---

<link rel="stylesheet" href="{{ '/eecs206a/assets/css/style.css' | relative_url }}">

<div class="hero">
  <div class="hero-content">
    <h1 class="hero-title">EECS 206A Final Project</h1>
    <p class="hero-subtitle">Hand–Eye Calibrated 3D Gaussian Splatting with a Robot Manipulator</p>
    <p class="hero-description">
      Active perception and metric 3D scene reconstruction via robot-controlled viewpoint acquisition
    </p>
  </div>
</div>

<div class="container">

  <!-- ================= INTRODUCTION ================= -->

  <section class="overview">
    <h2>1. Introduction</h2>

    <h3>(a) Objective</h3>
    <p>
      This project investigates the integration of robotic manipulation, hand–eye
      calibration, and neural scene representations to construct a metric 3D
      reconstruction system. A camera rigidly mounted to a robotic manipulator is
      actively repositioned to acquire multi-view observations of a scene. Using
      known robot kinematics and an estimated hand–eye transformation, all camera
      poses are expressed in a common world coordinate frame and used to train a
      3D Gaussian Splatting model.
    </p>

    <h3>(b) Motivation and Technical Challenges</h3>
    <p>
      Accurate 3D reconstruction is a foundational capability for robotic perception
      and manipulation. While classical structure-from-motion pipelines estimate
      camera poses visually, they often suffer from scale ambiguity, drift, and
      limited metric consistency. In contrast, leveraging robot-provided kinematics
      enables direct access to metric, repeatable camera poses. This approach,
      however, introduces challenges related to precise hand–eye calibration,
      synchronization between motion execution and image capture, and maintaining
      consistency across multiple coordinate frames throughout the reconstruction
      pipeline.
    </p>

    <h3>(c) Applications</h3>
    <p>
      The resulting system is applicable to a range of robotic tasks requiring
      accurate scene understanding, including grasp planning, bin picking,
      inspection, and the construction of digital twins for simulation and motion
      planning. The use of metric reconstructions aligned with the robot base frame
      facilitates downstream integration with manipulation and control algorithms.
    </p>
  </section>

  <!-- ================= DESIGN ================= -->

  <section class="features">
    <h2>2. System Design</h2>

    <h3>(a) Design Requirements</h3>
    <p>
      The system is required to produce metric 3D reconstructions aligned to the
      robot base frame, support repeatable and deterministic camera pose estimation
      via robot kinematics, and integrate seamlessly with motion planning and control
      software. Robustness to sensor noise and moderate calibration error is also a
      key consideration.
    </p>

    <h3>(b) Architecture</h3>
    <p>
      An RGB camera is rigidly mounted to the robot end-effector. A hand–eye
      calibration procedure estimates the fixed transformation between the camera
      and end-effector frames. The robot executes pre-planned trajectories to sample
      viewpoints around the scene. Camera poses are computed via forward kinematics
      composed with the hand–eye transformation and are provided directly to the
      3D Gaussian Splatting optimization process.
    </p>

    <h3>(c) Design Trade-offs</h3>
    <p>
      Utilizing robot-derived camera poses eliminates scale ambiguity and drift
      inherent to purely vision-based methods but makes reconstruction quality
      sensitive to calibration accuracy. 3D Gaussian Splatting was selected over
      voxel- or mesh-based representations due to its ability to capture fine
      geometric and appearance details, at the cost of increased training
      complexity and computational overhead.
    </p>

    <h3>(d) Engineering Considerations</h3>
    <p>
      The system prioritizes geometric accuracy and frame consistency over real-time
      performance, making it suitable for offline reconstruction workflows. Errors
      in calibration or kinematic modeling directly propagate into the learned scene
      representation, emphasizing the importance of careful system calibration and
      validation.
    </p>
  </section>

  <!-- ================= IMPLEMENTATION ================= -->

  <section class="methodology">
    <h2>3. Implementation</h2>

    <h3>(a) Hardware Setup</h3>
    <p>
      The experimental platform consists of a UR7e robotic manipulator equipped with
      a rigidly mounted Intel RealSense RGB camera. A custom camera mount ensures a
      fixed and repeatable transformation between the camera and the end-effector.
      The robot executes structured trajectories to capture images from diverse
      viewpoints around the target scene.
    </p>

    <h3>(b) Software Pipeline</h3>
    <p>
      Robot control, motion planning, and data collection are implemented using
      ROS2, with MoveIt handling inverse kinematics and trajectory execution.
      OpenCV is employed for calibration and image processing. Captured images and
      corresponding camera poses are processed using COLMAP and subsequently used
      to train a 3D Gaussian Splatting model, yielding the final scene
      representation.
    </p>
  </section>

  <!-- ================= RESULTS ================= -->

<section class="results">
  <h2>4. Results</h2>

<iframe
  loading="lazy"
  src="{{ '/eecs206a/viewer/viewer.html' | relative_url }}?splat={{ '/eecs206a/assets/models/point_cloud.spz' | relative_url }}"
  style="width:100%; height:500px; border:none; border-radius:12px;">
</iframe>


  <div class="results-gallery">
    <div class="result-item">
      <h3>3D Reconstruction Quality</h3>
      <p>
        The system produces dense 3D reconstructions exhibiting consistent geometry
        and appearance across viewpoints, demonstrating the effectiveness of
        robot-provided camera poses for metric scene reconstruction.
      </p>
    </div>

    <div class="result-item">
      <h3>Camera Trajectory Coverage</h3>
      <p>
        Executed trajectories provide comprehensive coverage of the scene, enabling
        stable optimization of the Gaussian Splatting representation.
      </p>
    </div>
  </div>
</section>


  <!-- ================= TECH ================= -->

  <section class="tech-stack">
    <h2>5. Technology Stack</h2>
    <div class="tech-list">
      <span class="tech-badge">ROS2</span>
      <span class="tech-badge">MoveIt</span>
      <span class="tech-badge">UR7e</span>
      <span class="tech-badge">Intel RealSense</span>
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
