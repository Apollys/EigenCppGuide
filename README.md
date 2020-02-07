# Eigen C++ Guide

## Types

Vectors:
```c++
Eigen::Vector2f  // vector of size 2 and datatype float
Eigen::Vector3d  // vector of size 3 and datatype double
Eigen::VectorXd  // vector of dynamic size and datatype double
```

Matricies:
```c++
Eigen::Matrix2d   // matrix of size 2x2 and datatype double
Eigen::Matrix2Xd  // matrix of size 2x? and datatype double
Eigen::MatrixX2d  // matrix of size ?x2 and datatype double
Eigen::MatrixXd   // matrix of dynamic size and datatype double
```

Transformations:
```c++
// Given the following variables...
Eigen::Vector3d point, bbox_center, bbox_size;
double bbox_yaw;
// Transform `point` into a 7-DoF bbox's frame
Eigen::Translation3d translation(-bbox_center);
Eigen::AngleAxisd rotation(-bbox_yaw, Eigen::Vector3d::UnitZ());
Eigen::Affine3d transform = rotation * translation;
Eigen::Vector3d transformed_point = transform * point;
```
