# EECS 206A Final Project Website

This is a GitHub Pages website for showcasing the EECS 206A Robotics final project.

## Project Overview

This project demonstrates an integrated robotics system that combines:
- Robotic manipulation using UR7e arm
- Multi-view image capture with RealSense camera
- Structure-from-motion using COLMAP
- 3D reconstruction using Gaussian Splatting

## Local Development

To run this site locally with Jekyll:

```bash
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000` in your browser.

## Customization

- Edit `index.html` to modify the main project page
- Edit `about.markdown` to update your personal information
- Edit `_config.yml` to change site-wide settings
- Add images to a `images/` or `assets/` folder and reference them in your pages

## Deployment

This site is automatically deployed to GitHub Pages when you push to the main branch. Make sure your repository settings have GitHub Pages enabled for the main branch.
