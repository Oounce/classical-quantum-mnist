#  Single pixel imaging with classical and quantum neutral network [classical-quantum-mnist]

Single-pixel cameras can be a great solution for the light outside of the visible spectrum. In combination with machine learning, they will allow to quickly obtain images for the practical applications. In the future of the development of quantum technologies, quantum computers can further speed up the solution of such problems. In this work we simulated a single-pixel detection experiment using Hadamard basis patterns, where images from the MNIST are used as objects. 64 measurements (6% of the number of pixels in the image) with maximum variance were selected. The algorithms for classifying and reconstucting images in single-pixel experiment using classical fully connected neural networks and quantum variational circuits were created. Quantum neural networks were used for the first time to solve this type of problem.

## Repository and models description

Here you can find four jupyther notebooks written in python. Every library you need need will be installed in notebooks, except torch.

<table>
    <tr>
        <th>Filename</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>Classical_Classification_with_noise.ipynb</td>
        <td>"single-pixel images" (64 measurements in Hadamard patterns basis) were classified using fully-connected linear network</td>
    </tr>
    <tr>
        <td>Classical_Reconstruction.ipynb</td>
        <td>"single-pixel images" were reconstrusted by the fully-connected linear network</td>
    </tr>
    <tr>
        <td>Quantum_Classification.ipynb</td>
        <td>"single-pixel images" were classified using quantum neural network (variational quantum circuits)</td>
    </tr>
    <tr>
        <td>Quantum_Reconstruction_dense.ipynb</td>
        <td>attempt of "single-pixel images" reconstruction using quantum neural network</td>
    </tr>
</table>

Each file consists of creating the dataset of measurements in single-pixel experiment from the MNIST, model and training (with loss plot).

### Models architecture

- Classical classifier
- Classical reconstruction
- Quantum classifier
- Quantum reconstruction

## Research results

- the classical classifier showed an accuracy of 97% after six training epochs
- the quantum classifier showed an accuracy of 93% after three (because simulating is too long) training epochs
- image reconstruction using a classical neural network showed 7% mean square error after six training epochs
- the quntum neural network for reconstructing didn't show good results. I assume that this is due to dense encoding and trying to relate probability measurements to image pixels. Measurements of this type turn out to be highly correlated as a result of calculations, since the qubits in the circuit become entangled. Thus, the model turned out to be unsuitable for solving such a problem.

**Here you can find the more detailed results of the study:** 
