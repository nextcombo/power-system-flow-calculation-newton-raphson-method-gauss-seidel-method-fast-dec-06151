# Power System Flow Calculation (Newton-Raphson Method, Gauss-Seidel Method, Fast Decoupling Method) [6-node, 9-node, 14-node, 26-node, 30-node, 57-node]

1. Overview
Initially, the calculation of power system flows was manually performed. Later, as the demand for the power system grew, computer networks were established, providing a material foundation for the calculation of power system flows. Power system flow calculations are fundamental to the analysis and calculation of power systems and indispensable tools for their operation and design. Based on the given operational conditions, network connections, and component parameters, flow calculations can determine the magnitude and phase angle of bus voltages, the power flowing through each element, and the overall system power loss.
In the planning and design of power systems as well as research on existing power system operating modes, flow calculations are essential for quantitatively analyzing and comparing the feasibility, reliability, and economic viability of supply schemes or operating modes. Moreover, power system flow calculations serve as the foundation for dynamic and static stability analysis in computer systems, making them an important and fundamental aspect of power system research. The development of power system flow calculations mainly revolves around these aspects: convergence of calculation methods, reliability; speed of computation; requirements for computer storage capacity, as well as ease and flexibility of computation.
This paper introduces simulation calculations based on Newton-Raphson method, Gaussian elimination method, and fast decoupling method for power system flow calculations, conducted in MATLAB.
2. Power System Flow Calculation Overview
2.1 Development of Power Flow Calculation
Initially, power system flow calculation relied on manual computations. To meet the growing needs of the power system, an alternating current (AC) calculator was introduced. With the advent of electronic digital computers in 1956, Ward and others developed a practical computer-based power flow calculation program. This marked a significant advancement for the increasingly complex large-scale power systems, providing powerful computational tools. Over decades of development, power system flow calculations have become highly mature. There are two forms of power system flow calculation: offline and online. The former is primarily used for planning and designing the power system, as well as determining the operational modes; the latter is employed for real-time monitoring and control of operating systems.The offline and online power flow calculations are the same in terms of calculation principles, all requiring: (1) a reliable and good convergence method; (2) less computer memory usage; (3) high computational speed; (4) a well-designed interface for ease of use.
2.2 Newton-Raphson Method for Power Flow Calculation
2.2.1 Node Voltage Equation
The power network equation refers to the mathematical equation group that summarizes the relevant parameters and variables of a network, reflecting its performance. It is not difficult to imagine that node voltage equations, loop current equations, and cut set voltage equations are among those that conform to this type of equation. However, due to the fact that cut set voltage equations are not commonly used in power system calculations, it is generally adopted to use either node voltage equations or loop current equations. However, since the parameters of current in the system are often difficult to measure and collect, and considering that there are many grounded branches in the equivalent network of the power system, the number of equation terms in the node voltage equation is relatively small. The modification coefficient is also convenient when the network structure changes or the transformer ratio changes. Therefore, the node voltage equation has its distinct advantages.
2.2.2 Node Impedance Matrix
The node impedance matrix and the node impedance matrix are both square matrices, with the order equal to the number of nodes (n) except for the reference node. However, we often adopt the node impedance matrix in power flow calculations because it is a sparse matrix. The number of non-zero elements on each row equals the number of ungrounded branches connected to the node i. Since there is no direct connection between nodes i and j, the value is zero, which is very common in practical power systems. Therefore, using the node impedance matrix facilitates modifications to the system structure.
2.2.3 Non-Standard Ratio Transformer Equivalent Circuit
For the equivalent circuit model of transformers, there are type equivalent circuit models and T-type equivalent transformer models. However, neither of these can reflect the actual voltage transformation function of transformers. It is necessary to normalize all parameters and variables to the same voltage level. However, the equivalent transformer model can represent the voltage transformation function of transformers and is also the transformer model used in computer-based power system analysis. Although this model does not exclude manual calculations.
Firstly, as shown in Figure 3-2-3(a), the reactance or excitation branch of the transformer can be omitted. For a double-winding transformer, an equivalent circuit can be represented by connecting an impedance to an ideal transformer in series. The ideal transformer is merely a parameter, which is the ratio of turns. Now, assuming the transformer impedance is normalized to the low-voltage side for example, we derive the equivalent circuit of the transformer.
Editor
The power flowing into and out of the ideal transformer is equal when the impedance of the transformer is normalized to the low-voltage side:
For more detailed articles, see Part Four:
Editor
3 Simulation Results
4 Matlab Code and Article Explanation This article only showcases part of the code; all codes are available here:
clear all\nclc\nch = input('Enter the node power flow you want to calculate..: (6Node 9Node 14Node 26Node 30Node 57Node): ');\nwhile ch ~= 6 && ch ~= 14 && ch ~= 26 && ch ~= 30 && ch ~= 57 && ch ~= 9\n    fprintf('Invalid input, please try again.\n');\n    ch = input('Enter the node power flow you want to calculate..: (6Node 9Node 14Node 26Node 30Node 57Node): ');\nend\nswitch ch\n    case 6\n        data6\n    case 14\n        data14\n    case 26\n        data26\n    case 30\n        data30\n    case 57\n        data57\n    case 9\n        data9\nend\nmet = input('Enter the method you want to select for calculating power flow. (1 - Gauss-Seidel method, 2 - Newton-Raphson method, 3 - Fast decoupling method): ');\nwhile met ~= 1 && met ~= 2 && met ~= 3\n    fprintf('Invalid input, please try again.\n');\n    met = input('Enter the method you want to select for calculating power flow. (1 - Gauss-Seidel method, 2 - Newton-Raphson method, 3 - Fast decoupling method):  ');\nend\nswitch met\n    case 1\n        maingauss\n    case 2\n        mainnewton\n    case 3\n        maindecouple\nend\n  
​  

## Images

![Power System Flow Calculation (Newton-Raphson Method, Gauss-Seidel Method, Fast Decoupling Method) [6 nodes, 9 nodes, 14 nodes, 26 nodes, 30 nodes, 57 nodes]](01.png)
![Power System Flow Calculation (Newton-Raphson Method, Gauss-Seidel Method, Fast Decoupling Method) [6 nodes, 9 nodes, 14 nodes, 26 nodes, 30 nodes, 57 nodes]](02.png)
![Power System Flow Calculation (Newton-Raphson Method, Gauss-Seidel Method, Fast Decoupling Method) [6 nodes, 9 nodes, 14 nodes, 26 nodes, 30 nodes, 57 nodes]](03.png)
![Power System Flow Calculation (Newton-Raphson Method, Gauss-Seidel Method, Fast Decoupling Method) [6 nodes, 9 nodes, 14 nodes, 26 nodes, 30 nodes, 57 nodes]](04.png)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
