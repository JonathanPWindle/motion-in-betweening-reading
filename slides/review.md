# Robust Motion In-betweening
---
Félix G. Harvey and Mike Yurick and Derek Nowrouzezahrai and Christopher Pal

![header](../assets/header.png)

---

## Goal

Generate human 3D motion between key frames

<video data-autoplay src="../assets/example.mp4"></video>

---

## Prior work

* Non-Generative
    * Requires motion database
    * Not scalable

---

### Dataset - LAFan1
* Subset of H36M
* Used a skeleton model of J=28 (H36M) and J=22 (LaFAN1)
* Represented using:
    * Quaternian vector $q_t$ of $j * 4$ dimensions encoding rotation
    * 3-dimensional global root velocity vector $r_t$
    * Contact information based on toes and feet velocities as a binary vector $c_t$ of 4-dimensions

---

### Dataset - LAFan1
* Rotate each input sequence seen by the network around the $Y$ axis (up) so that the root of the skeleton points towards the $X_+$ axis on the last frame of past context
    *  Store the applied rotation in order to rotate back the generated motion to fit the context

---

### Architecture 
![architecture](../assets/top-level.png)