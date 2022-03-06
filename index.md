
**Abstract:**

Many challenging robotic manipulation problems can be viewed through the lens of a sequence of pick and pick-conditioned place actions. Recently, Transporter Net proposed a framework for pick and place that is able to learn good manipulation policies from a very few expert demonstrations. A key reason why Transporter Net is so sample efficient is that the model incorporates rotational equivariance into the pick-conditioned place module, i.e., the model immediately generalizes learned pick-place knowledge to objects presented in different pick orientations. This work proposes a novel version of Transporter Net that is equivariant to both pick and place orientation. As a result, our model immediately generalizes pick-place knowledge to different place orientations in addition to generalizing pick orientation as before. Ultimately, our new model is more sample efficient and achieves better pick and place success rates than the baseline Transporter Net model. Our experiments show that only with 10 expert demonstrations, Equivariant Transporter Net can achieve greater than 95% success rate on 7/10 tasks of unseen configurations of Ravens-10 Benchmark. Finally, we augment our model with the ability to grasp using a parallel-jaw gripper rather than just a suction cup and demonstrate it on both simulation tasks and a real robot.

<style>
.column {
  float: left;
  width: 33.33%;
}
.lc{
  float: left;
  width: 16.66%;
}
.caption {
    margin: 0;
    vertical-align: baseline;
    text-align: center;
}

.column_l {
  float: left;
  width: 40.00%;
}
.lc{
  float: left;
  width: 16.66%;
}
.caption {
    margin: 0;
    vertical-align: baseline;
    text-align: center;
}

.column_r {
  float: right;
  width: 40.00%;
}
.lc{
  float: left;
  width: 16.66%;
}
.caption {
    margin: 0;
    vertical-align: baseline;
    text-align: center;
}

.column_m {
  float: left;
  width: 20.00%;
}
.lc{
  float: left;
  width: 16.66%;
}
.caption {
    margin: 0;
    vertical-align: baseline;
    text-align: center;
}



img.rounded {
  object-fit: cover;
  border-radius: 50%;
  height: 120px;
  width: 120px;
  margin-left: auto;
  margin-right: auto;
  display: block;
}
.people_column {
  float: left;
  width: 150px;
}
</style>

## Paper &nbsp;&nbsp; &nbsp;&nbsp; [PDF](https://arxiv.org/abs/2202.09400)&nbsp;&nbsp;•&nbsp;&nbsp; [CODE](https://github.com/HaojHuang/Equivariant-Transporter-Net)&nbsp;&nbsp;•&nbsp;&nbsp;

<div style="width:100%; display:flex">
  
<div class="people_column">
    <img src="img/haojie.jpg" class="rounded">
    <p class="caption">
      <a href="https://haojhuang.github.io">Haojie Huang</a>
    </p>
  </div>

  <div class="people_column">
    <img src="img/dian.jpeg" class="rounded">
    <p class="caption">
      <a href="https://pointw.github.io">Dian Wang</a>
    </p>
  </div>

  <div class="people_column">
    <img src="img/robin.jpeg" class="rounded">
    <p class="caption">
      <a href="http://mathserver.neu.edu/robin/">Robin Walters</a>
    </p>
  </div>

  <div class="people_column">
    <img src="img/rob.jpeg" class="rounded">
    <p class="caption">
      <a href="http://www.ccs.neu.edu/home/rplatt/">Robert Platt</a>
    </p>
  </div>

</div>

&nbsp;&nbsp; &nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp; Khoury College of Computer Sciences, Northeastern University

## Elevator Pitch

### Equivariance in Pick and Place

Pick and place is an important topic in manipulation due to its value in industry. Traditional assembly methods in factories require customized workstations so that fixed pick and place actions can be manually predefined. Recently, considerable research has focused on end-to-end visioned based models that directly map input observations to actions, which can learn quickly and generalize well. However, due to the large action space, these methods often require copious amounts of data.

A recent sample-efficient framework, Transporter Net, detects the pick-conditioned place pose by performing the cross convolution between an encoding of the scene and an encoding of a stack of differently rotated image patches around the pick. As  a  result  of  this  design,  Transporter Net is equivariant with respect to pick orientation. As shown in the left figure below, if the model can correctly pick the pink object and place it inside the green outline when the object is presented in one orientation, it is automatically able to pick and place the same object when it is presented in a different orientation.  This symmetry over object orientation enables Transporter Net to generalize well and it is fundamentally linked to the sample efficiency of the model. Assuming that pick orientation is discretized into n possible gripper rotations, we will refer to this as a C_n pick symmetry, where C_n is the finite cyclic subgroup of SO(2) that denotes a set of $n$ rotations.

Although Transporter Net is C_n-equivariant with regard to pick, the model does not have a similar equivariance with regard to place. That is, if the model learns how to place an object in one orientation, that knowledge does not generalize immediately to different place orientations. This work seeks to add this type of equivariance to the Transporter Network model by incorporating C_n-equivarant convolutional layers into both the pick and place models. Our resulting model is equivariant both to changes in pick object orientation and changes in place orientation. This symmetry is illustrated in right figure below and can be viewed as a direct product of two cyclic groups, C_n \times C_n. Enforcing equivariance with respect to an even larger symmetry group than Transporter Net leads to even greater sample efficiency since equivariant neural networks learn effectively on a lower dimensional action space, the equivalence classes of samples under the group action. Thus a larger group results in an even smaller dimensional sample space and thus better coverage by the training data.

<div>
  <div class="column_l">
    <img src="img/cn.png" style="width:100%">
    <p class="caption"> C_n Equivariance</p>
  </div>
  
  <div class="column_m">
    <img src="img/blank.png" style="width:100%">
    <p class="caption"></p>
  </div>
  
  <div class="column_l">
    <img src="img/cn_by_cn.png" style="width:100%">
    <p class="caption"> C_n times C_n Equivariance </p>
  </div>
</div>

## Highlight

<p align="center">
  <img src="img/gripper.png" width="1000px">
</p>

<div>
  <div class="column">
    <img src="img/block-insertion.gif" style="width:100%">
    <p class="caption">Block Insertion</p>
  </div>
  <div class="column">
    <img src="img/place-boxes-in-bowls.gif" style="width:100%">
    <p class="caption">Place Boxes in Bowls </p>
  </div>
  <div class="column">
    <img src="img/stack-block-pyramid.gif" style="width:100%">
    <p class="caption">Stack Block Pyramid</p>
  </div>
</div>


<p></p><br>


## Citation

## Contact

