# Image Optimization
During the optimization process for image processing functions, various techniques were employed to enhance performance. For the "Rotate" function, optimization methods like constant folding, function inlining, code motion, and loop fusion were put to the test.

Function inlining proved to be beneficial, as it eliminated the need for repetitive memory allocation and activation record creation. By inlining the function with three constant parameters performing the same task, the overall performance improved.

Constant folding and code motion were effective in optimizing variables. Variables declared outside the loop, which remained unchanged throughout the loop execution, benefited from code motion. Strength reduction was also applied, replacing multiplications with additions wherever possible (e.g., k += dim), leading to enhanced efficiency. Loop fusion, another optimization technique, reduced memory usage and improved overall cycle time.

The most impactful optimization was achieved by modifying the loops, thereby enhancing locality and improving array access, resulting in better performance.

For the "Smooth" function, loop inlining and code motion were the primary techniques tested.

Loop inlining was applied to reduce the frequency of calls to the average function within the for-loops. Inlining other functions like accumulate_sum(), minimum(), maximum(), and assign_sum_to_pixel() also contributed to performance improvements.

Code motion was employed for variables like sum.red, sum.green, sum.blue, and sum.num outside the two for-loops, allowing their initialization before the loops for enhanced efficiency.

Among the optimization techniques applied, loop inlining stood out as the most beneficial, significantly boosting performance and reducing cycle time by incorporating function code directly into the loop. This eliminated the need for separate sets of instructions in memory for each function, simplifying access and execution.

The optimization efforts resulted in substantial performance gains, making the image processing functions more efficient and capable of handling larger datasets with improved speed and resource utilization.
