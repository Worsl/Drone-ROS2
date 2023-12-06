# ParrotSphinx Custom Model and Calibration Files

## Model Files and configuration.yaml

To integrate custom models into the ParrotSphinx environment, a model file in the .fbx format is required. This file can be generated using any 3D modeling software of your choice. In this guide, we'll briefly outline the process and highlight the use of Blender as a preferred tool for creating model files.

### How to Use Custom Model Files in ParrotSphinx:

1. **Create a Model (creating the mesh):**
   - Use a 3D modeling software (such as Blender in my case) to design and export your model from PDF to the .fbx format.

![Alt text](image.png)
![Alt text](image-3.png)
2. **Load the Model into ParrotSphinx:**
   - Place the generated .fbx file in the designated directory within the ParrotSphinx environment. Note that sphinx only supports .fbx files
   - When launching ParrotSphinx, specify the custom model file to be loaded into the simulation environment.    specify the filepath which contains the config_file.yaml



```bash
parrot-ue4-empty -config-file=<filepath/config_file.yaml> # in terminal
```

```yaml
# This is the config_file.yaml
Meshes:
  - Name: 'check-108'
    FbxPath: "/home/cheng/Desktop/check-108.fbx"
    Location: "0 10 100"
    Rotation: "0 90 90"
    Scale: "0.1 0.1 0.1"
    SnapToGround: false
```

Explanation:

- **Meshes:** This is a list indicating that multiple meshes can be defined in this configuration. In this case, there is only one mesh defined.

- **Name:** The identifier or name given to the mesh. In this example, the mesh is named 'check-108'.

- **FbxPath:** The file path to the .fbx (3D model) file. In this example, the path is "/home/cheng/Desktop/check-108.fbx". This specifies the location of the 3D model file on the filesystem.

- **Location:** The position of the mesh in the 3D space. It is specified as a set of three coordinates (x, y, z). In this case, the mesh is located at coordinates (0, 10, 100).

- **Rotation:** The rotation of the mesh in the 3D space, specified as a set of three angles (in degrees) around the x, y, and z axes. In this example, the rotation is (0, 90, 90), indicating rotations around these axes.

- **Scale:** The scaling factor applied to the mesh in the x, y, and z dimensions. In this example, the mesh is scaled by a factor of 0.1 in each dimension.

- **SnapToGround:** A boolean parameter indicating whether the mesh should be snapped to the ground or not. In this case, it is set to `false`, suggesting that the mesh is not forced to align with the ground.

 

   Adjust the `model_filename.fbx` with the actual name of your custom model file.

   ![Alt text](image-1.png)

3. **Experiment and Test:**
   - Run simulations with your custom model to ensure compatibility and proper integration into the ParrotSphinx environment.

## Calibration Files

The calibration files include essential data obtained through the calibration process, specifically tailored for a 4K drone within the ParrotSphinx environment. The calibration data is stored in a compressed archive file named `calibrationdata.tar.gz`. This archive encompasses:

- **Images:**
  - Collection of images taken within the ParrotSphinx environment during the calibration process.

- **Calibration Outcome:**
  - Calibration results are provided in two formats:
    - Calibration outcome in a plain text file (.txt).
    - Calibration outcome in a YAML file (.yaml).

### How to Use Calibration Files:

1. **Extract Calibration Files:**
   - Extract the contents of the `calibrationdata.tar.gz` archive to access the images and calibration outcome files.

   ```bash
   tar -zxvf calibrationdata.tar.gz
   ```

2. **Review Calibration Data:**
   - Explore the images and review the calibration results in both the .txt and .yaml files.

![Alt text](image-2.png)