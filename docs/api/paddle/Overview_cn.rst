.. _cn_overview_paddle:

paddle
---------------------

paddle 目录下包含tensor、device、framework相关API以及某些高层API。具体如下：

-  :ref:`tensor数学操作 <tensor_math>`
-  :ref:`tensor逻辑操作 <tensor_logic>`
-  :ref:`tensor属性相关 <tensor_attribute>`
-  :ref:`tensor创建相关 <tensor_creation>`
-  :ref:`tensor元素查找相关 <tensor_search>`
-  :ref:`tensor初始化相关 <tensor_initializer>`
-  :ref:`tensor random相关 <tensor_random>`
-  :ref:`tensor线性代数相关 <tensor_linalg>`
-  :ref:`tensor元素操作相关（如：转置，reshape等） <tensor_manipulation>`
-  :ref:`爱因斯坦求和 <einsum>`
-  :ref:`framework相关 <about_framework>`
-  :ref:`device相关 <about_device>`
-  :ref:`高层API相关 <about_hapi>`




.. _tensor_math:

tensor数学操作
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.abs <cn_api_fluid_layers_abs>` ", "绝对值函数"
    " :ref:`paddle.angle <cn_api_paddle_angle>` ", "相位角函数"
    " :ref:`paddle.acos <cn_api_fluid_layers_acos>` ", "arccosine函数"
    " :ref:`paddle.add <cn_api_tensor_add>` ", "Tensor逐元素相加"
    " :ref:`paddle.add_n <cn_api_tensor_add_n>` ", "对输入的一至多个Tensor或LoDTensor求和"
    " :ref:`paddle.addmm <cn_api_tensor_addmm>` ", "计算输入Tensor x和y的乘积，将结果乘以标量alpha，再加上input与beta的乘积，得到输出"
    " :ref:`paddle.all <cn_api_tensor_all>` ", "对指定维度上的Tensor元素进行逻辑与运算"
    " :ref:`paddle.allclose <cn_api_tensor_allclose>` ", "逐个检查输入Tensor x和y的所有元素是否均满足 ∣x−y∣≤atol+rtol×∣y∣"
    " :ref:`paddle.isclose <cn_api_tensor_isclose>` ", "逐个检查输入Tensor x和y的所有元素是否满足 ∣x−y∣≤atol+rtol×∣y∣"
    " :ref:`paddle.any <cn_api_tensor_any>` ", "对指定维度上的Tensor元素进行逻辑或运算"
    " :ref:`paddle.asin <cn_api_fluid_layers_asin>` ", "arcsine函数"
    " :ref:`paddle.atan <cn_api_fluid_layers_atan>` ", "arctangent函数"
    " :ref:`paddle.atan2 <cn_api_paddle_atan2>` ", "arctangent2函数"
    " :ref:`paddle.ceil <cn_api_fluid_layers_ceil>` ", "向上取整运算函数"
    " :ref:`paddle.clip <cn_api_tensor_clip>` ", "将输入的所有元素进行剪裁，使得输出元素限制在[min, max]内"
    " :ref:`paddle.conj <cn_api_tensor_conj>` ", "逐元素计算Tensor的共轭运算"
    " :ref:`paddle.cos <cn_api_fluid_layers_cos>` ", "余弦函数"
    " :ref:`paddle.cosh <cn_api_fluid_layers_cosh>` ", "双曲余弦函数"
    " :ref:`paddle.cumsum <cn_api_tensor_cn_cumsum>` ", "沿给定 axis 计算张量 x 的累加和"
    " :ref:`paddle.cumprod <cn_api_tensor_cn_cumprod>` ", "沿给定 dim 计算张量 x 的累乘"
    " :ref:`paddle.digamma <cn_api_paddle_digamma>` ", "逐元素计算输入x的digamma函数值"
    " :ref:`paddle.divide <cn_api_tensor_divide>` ", "逐元素相除算子"
    " :ref:`paddle.equal <cn_api_tensor_equal>` ", "该OP返回 x==y 逐元素比较x和y是否相等，相同位置的元素相同则返回True，否则返回False"
    " :ref:`paddle.equal_all <cn_api_tensor_equal_all>` ", "如果所有相同位置的元素相同返回True，否则返回False"
    " :ref:`paddle.erf <cn_api_fluid_layers_erf>` ", "逐元素计算 Erf 激活函数"   
    " :ref:`paddle.exp <cn_api_fluid_layers_exp>` ", "逐元素进行以自然数e为底指数运算"
    " :ref:`paddle.expm1 <cn_api_paddle_expm1>` ", "逐元素进行exp(x)-1运算"
    " :ref:`paddle.floor <cn_api_fluid_layers_floor>` ", "向下取整函数"  
    " :ref:`paddle.floor_divide <cn_api_tensor_floor_divide>` ", "逐元素整除算子，输入 x 与输入 y 逐元素整除，并将各个位置的输出元素保存到返回结果中"
    " :ref:`paddle.greater_equal <cn_api_tensor_cn_greater_equal>` ", "逐元素地返回 x>=y 的逻辑值"
    " :ref:`paddle.greater_than <cn_api_tensor_cn_greater_than>` ", "逐元素地返回 x>y 的逻辑值"
    " :ref:`paddle.increment <cn_api_tensor_increment>` ", "在控制流程中用来让 x 的数值增加 value"
    " :ref:`paddle.kron <cn_api_paddle_tensor_kron>` ", "计算两个张量的克罗内克积"
    " :ref:`paddle.less_equal <cn_api_tensor_cn_less_equal>` ", "逐元素地返回 x<=y 的逻辑值"
    " :ref:`paddle.less_than <cn_api_tensor_cn_less_than>` ", "逐元素地返回 x<y 的逻辑值"
    " :ref:`paddle.lgamma <cn_api_paddle_lgamma>` ", "计算输入 x 的 gamma 函数的自然对数并返回"
    " :ref:`paddle.log <cn_api_fluid_layers_log>` ", "Log激活函数（计算自然对数）"
    " :ref:`paddle.log10 <cn_api_paddle_tensor_math_log10>` ", "Log10激活函数（计算底为10的对数）" 
    " :ref:`paddle.log2 <cn_api_paddle_tensor_math_log2>` ", "计算Log1p（加一的自然对数）结果"
    " :ref:`paddle.logical_and <cn_api_fluid_layers_logical_and>` ", "逐元素的对 x 和 y 进行逻辑与运算"
    " :ref:`paddle.logical_not <cn_api_fluid_layers_logical_not>` ", "逐元素的对 X Tensor进行逻辑非运算"
    " :ref:`paddle.logical_or <cn_api_fluid_layers_logical_or>` ", "逐元素的对 X 和 Y 进行逻辑或运算"
    " :ref:`paddle.logical_xor <cn_api_fluid_layers_logical_xor>` ", "逐元素的对 X 和 Y 进行逻辑异或运算"
    " :ref:`paddle.logit <cn_api_tensor_logit>` ", "计算logit结果"
    " :ref:`paddle.bitwise_and <cn_api_tensor_bitwise_and>` ", "逐元素的对 x 和 y 进行按位与运算"
    " :ref:`paddle.bitwise_not <cn_api_tensor_bitwise_not>` ", "逐元素的对 X Tensor进行按位取反运算"
    " :ref:`paddle.bitwise_or <cn_api_tensor_bitwise_or>` ", "逐元素的对 X 和 Y 进行按位或运算"
    " :ref:`paddle.bitwise_xor <cn_api_tensor_bitwise_xor>` ", "逐元素的对 X 和 Y 进行按位异或运算"
    " :ref:`paddle.logsumexp <cn_api_paddle_tensor_math_logsumexp>` ", "沿着 axis 计算 x 的以e为底的指数的和的自然对数"
    " :ref:`paddle.max <cn_api_paddle_tensor_max>` ", "对指定维度上的Tensor元素求最大值运算"
    " :ref:`paddle.maximum <cn_api_paddle_tensor_maximum>` ", "逐元素对比输入的两个Tensor，并且把各个位置更大的元素保存到返回结果中"
    " :ref:`paddle.mean <cn_api_tensor_cn_mean>` ", "沿 axis 计算 x 的平均值"
    " :ref:`paddle.median <cn_api_tensor_cn_median>` ", "沿给定的轴 axis 计算 x 中元素的中位数"
    " :ref:`paddle.min <cn_api_paddle_tensor_min>` ", "对指定维度上的Tensor元素求最小值运算"
    " :ref:`paddle.minimum <cn_api_paddle_tensor_minimum>` ", "逐元素对比输入的两个Tensor，并且把各个位置更小的元素保存到返回结果中"
    " :ref:`paddle.mm <cn_api_tensor_mm>` ", "用于两个输入矩阵的相乘"
    " :ref:`paddle.multiplex <cn_api_fluid_layers_multiplex>` ", "从每个输入Tensor中选择特定行构造输出Tensor"   
    " :ref:`paddle.multiply <cn_api_fluid_layers_multiply>` ", "逐元素相乘算子"
    " :ref:`paddle.neg <cn_api_paddle_neg>` ", "计算输入 x 的相反数并返回"
    " :ref:`paddle.not_equal <cn_api_tensor_not_equal>` ", "逐元素地返回x!=y 的逻辑值"
    " :ref:`paddle.pow <cn_api_paddle_tensor_math_pow>` ", "指数算子，逐元素计算 x 的 y 次幂"   
    " :ref:`paddle.prod <cn_api_tensor_cn_prod>` ", "对指定维度上的Tensor元素进行求乘积运算"
    " :ref:`paddle.reciprocal <cn_api_fluid_layers_reciprocal>` ", "对输入Tensor取倒数"
    " :ref:`paddle.round <cn_api_fluid_layers_round>` ", "将输入中的数值四舍五入到最接近的整数数值"
    " :ref:`paddle.rsqrt <cn_api_fluid_layers_rsqrt>` ", "rsqrt激活函数"
    " :ref:`paddle.scale <cn_api_fluid_layers_scale>` ", "缩放算子"
    " :ref:`paddle.sign <cn_api_tensor_sign>` ", "对输入x中每个元素进行正负判断"
    " :ref:`paddle.sin <cn_api_fluid_layers_sin>` ", "计算输入的正弦值"
    " :ref:`paddle.sinh <cn_api_fluid_layers_sinh>` ", "双曲正弦函数"
    " :ref:`paddle.sqrt <cn_api_fluid_layers_sqrt>` ", "计算输入的算数平方根"
    " :ref:`paddle.square <cn_api_fluid_layers_square>` ", "该OP执行逐元素取平方运算"
    " :ref:`paddle.stanh <cn_api_fluid_layers_stanh>` ", "stanh 激活函数"
    " :ref:`paddle.std <cn_api_tensor_cn_std>` ", "沿给定的轴 axis 计算 x 中元素的标准差"
    " :ref:`paddle.subtract <cn_api_paddle_tensor_subtract>` ", "逐元素相减算子"
    " :ref:`paddle.sum <cn_api_tensor_sum>` ", "对指定维度上的Tensor元素进行求和运算"
    " :ref:`paddle.tan <cn_api_fluid_layers_tan>` ", "三角函数tangent"
    " :ref:`paddle.tanh <cn_api_tensor_tanh>` ", "tanh激活函数"
    " :ref:`paddle.tanh_ <cn_api_tensor_tanh_>` ", "Inplace 版本的 tanh API，对输入 x 采用 Inplace 策略"
    " :ref:`paddle.trace <cn_api_tensor_trace>` ", "计算输入 Tensor 在指定平面上的对角线元素之和"
    " :ref:`paddle.var <cn_api_tensor_cn_var>` ", "沿给定的轴 axis 计算 x 中元素的方差"
    " :ref:`paddle.diagonal <cn_api_tensor_diagonal>` ", "根据给定的轴 axis 返回输入 Tensor 的局部视图"
    " :ref:`paddle.trunc <cn_api_tensor_trunc>` ", "对输入 Tensor 每个元素的小数部分进行截断"
    " :ref:`paddle.log1p <cn_api_paddle_tensor_log1p>` ", "该OP计算Log1p（加一的自然对数）结果"
    " :ref:`paddle.lerp <cn_api_paddle_tensor_lerp>` ", "该OP基于给定的 weight 计算 x 与 y 的线性插值"
    " :ref:`paddle.diff <cn_api_tensor_diff>` ", "沿着指定维度对输入Tensor计算n阶的前向差值"
    " :ref:`paddle.rad2deg <cn_api_paddle_tensor_rad2deg>` ", "将元素从弧度的角度转换为度"
    " :ref:`paddle.deg2rad <cn_api_paddle_tensor_deg2rad>` ", "将元素从度的角度转换为弧度"
    " :ref:`paddle.gcd <cn_api_paddle_tensor_gcd>` ", "计算两个输入的按元素绝对值的最大公约数"
    " :ref:`paddle.lcm <cn_api_paddle_tensor_lcm>` ", "计算两个输入的按元素绝对值的最小公倍数"


.. _tensor_logic:

tensor逻辑操作
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.is_empty <cn_api_fluid_layers_is_empty>` ", "测试变量是否为空"
    " :ref:`paddle.is_tensor <cn_api_tensor_is_tensor>` ", "用来测试输入对象是否是paddle.Tensor"
    " :ref:`paddle.isfinite <cn_api_tensor_isfinite>` ", "返回输入tensor的每一个值是否为Finite（既非 +/-INF 也非 +/-NaN ）"
    " :ref:`paddle.isinf <cn_api_tensor_isinf>` ", "返回输入tensor的每一个值是否为 +/-INF"
    " :ref:`paddle.isnan <cn_api_tensor_isnan>` ", "返回输入tensor的每一个值是否为 +/-NaN"

.. _tensor_attribute:

tensor属性相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.imag <cn_api_tensor_imag>` ", "返回一个包含输入复数Tensor的虚部数值的新Tensor"
    " :ref:`paddle.real <cn_api_tensor_real>` ", "返回一个包含输入复数Tensor的实部数值的新Tensor"
    " :ref:`paddle.shape <cn_api_fluid_layers_shape>` ", "获得输入Tensor或SelectedRows的shape"
    " :ref:`paddle.broadcast_shape <cn_api_tensor_broadcast_shape>` ", "返回对x_shape大小的张量和y_shape大小的张量做broadcast操作后得到的shape"

.. _tensor_creation:

tensor创建相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.arange <cn_api_paddle_tensor_arange>` ", "返回以步长 step 均匀分隔给定数值区间[start, end)的1-D Tensor，数据类型为 dtype"
    " :ref:`paddle.diag <cn_api_paddle_cn_diag>` ", "如果 x 是向量（1-D张量），则返回带有 x 元素作为对角线的2-D方阵;如果 x 是矩阵（2-D张量），则提取 x 的对角线元素，以1-D张量返回。"
    " :ref:`paddle.diagflat <cn_api_paddle_diagflat>` ", "如果 x 是一维张量，则返回带有 x 元素作为对角线的二维方阵;如果 x 是大于等于二维的张量，则返回一个二维张量，其对角线元素为 x 在连续维度展开得到的一维张量的元素。"
    " :ref:`paddle.empty <cn_api_tensor_empty>` ", "创建形状大小为shape并且数据类型为dtype的Tensor"
    " :ref:`paddle.empty_like <cn_api_tensor_empty_like>` ", "根据 x 的shape和数据类型 dtype 创建未初始化的Tensor"
    " :ref:`paddle.eye <cn_api_paddle_tensor_eye>` ", "构建二维Tensor(主对角线元素为1，其他元素为0)"
    " :ref:`paddle.full <cn_api_tensor_full>` ", "创建形状大小为 shape 并且数据类型为 dtype 的Tensor"
    " :ref:`paddle.full_like <cn_api_tensor_full_like>` ", "创建一个和 x 具有相同的形状并且数据类型为 dtype 的Tensor"
    " :ref:`paddle.linspace <cn_api_fluid_layers_linspace>` ", "返回一个Tensor，Tensor的值为在区间start和stop上均匀间隔的num个值，输出Tensor的长度为num"
    " :ref:`paddle.meshgrid <cn_api_paddle_tensor_meshgrid>` ", "对每个张量做扩充操作"
    " :ref:`paddle.numel <cn_api_tensor_numel>` ", "返回一个长度为1并且元素值为输入 x 元素个数的Tensor"  
    " :ref:`paddle.ones <cn_api_tensor_ones>` ", "创建形状为 shape 、数据类型为 dtype 且值全为1的Tensor"
    " :ref:`paddle.ones_like <cn_api_tensor_ones_like>` ", "返回一个和 x 具有相同形状的数值都为1的Tensor"
    " :ref:`paddle.Tensor <cn_api_paddle_Tensor>` ", "Paddle中最为基础的数据结构"
    " :ref:`paddle.to_tensor <cn_api_vision_transforms_to_tensor>` ", "通过已知的data来创建一个tensor"
    " :ref:`paddle.tolist <cn_api_paddle_tolist>` ", "将paddle Tensor转化为python list"
    " :ref:`paddle.zeros <cn_api_tensor_zeros>` ", "该OP创建形状为 shape 、数据类型为 dtype 且值全为0的Tensor"
    " :ref:`paddle.zeros_like <cn_api_tensor_zeros_like>` ", "该OP返回一个和 x 具有相同的形状的全零Tensor，数据类型为 dtype 或者和 x 相同"
    " :ref:`paddle.create_parameter <cn_api_paddle_create_parameter>` ", "该OP创建一个参数,该参数是一个可学习的变量, 拥有梯度并且可优化"
    " :ref:`paddle.batch <cn_api_paddle_batch>` ", "一个reader的装饰器。返回的reader将输入reader的数据打包成指定的batch_size大小的批处理数据(不推荐使用)"

.. _tensor_search:

tensor元素查找相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.argmax <cn_api_tensor_argmax>` ", "沿 axis 计算输入 x 的最大元素的索引"
    " :ref:`paddle.argmin <cn_api_tensor_argmin>` ", "沿 axis 计算输入 x 的最小元素的索引"
    " :ref:`paddle.argsort <cn_api_tensor_cn_argsort>` ", "对输入变量沿给定轴进行排序，输出排序好的数据的相应索引，其维度和输入相同"
    " :ref:`paddle.index_sample <cn_api_tensor_search_index_sample>` ", "对输入 x 中的元素进行批量抽样"
    " :ref:`paddle.index_select <cn_api_tensor_search_index_select>` ", "沿着指定轴 axis 对输入 x 进行索引"
    " :ref:`paddle.masked_select <cn_api_tensor_masked_select>` ", "返回一个1-D 的Tensor, Tensor的值是根据 mask 对输入 x 进行选择的"
    " :ref:`paddle.nonzero <cn_api_tensor_search_nonzero>` ", "返回输入 x 中非零元素的坐标"
    " :ref:`paddle.sort <cn_api_tensor_sort>` ", "对输入变量沿给定轴进行排序，输出排序好的数据，其维度和输入相同"
    " :ref:`paddle.searchsorted <cn_api_tensor_searchsorted>` ", "将根据给定的 values 在 sorted_sequence 的最后一个维度查找合适的索引"
    " :ref:`paddle.topk <cn_api_tensor_cn_topk>` ", "沿着可选的 axis 查找topk最大或者最小的结果和结果所在的索引信息"
    " :ref:`paddle.where <cn_api_tensor_where>` ", "该OP返回一个根据输入 condition, 选择 x 或 y 的元素组成的多维 Tensor"

.. _tensor_initializer:

tensor初始化相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.assign <cn_api_paddle_tensor_creation_assign>` ", "将输入Tensor或numpy数组拷贝至输出Tensor"

.. _tensor_random:

tensor random相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.bernoulli <cn_api_tensor_bernoulli>` ", "以输入 x 为概率，生成一个伯努利分布（0-1分布）的Tensor，输出Tensor的形状和数据类型与输入 x 相同"
    " :ref:`paddle.multinomial <cn_api_tensor_multinomial>` ", "以输入 x 为概率，生成一个多项分布的Tensor"
    " :ref:`paddle.normal <cn_api_tensor_random_normal>` ", "返回符合正态分布（均值为 mean ，标准差为 std 的正态随机分布）的随机Tensor"
    " :ref:`paddle.rand <cn_api_tensor_random_rand>` ", "返回符合均匀分布的，范围在[0, 1)的Tensor"
    " :ref:`paddle.randint <cn_api_tensor_random_randint>` ", "返回服从均匀分布的、范围在[low, high)的随机Tensor"
    " :ref:`paddle.randint_like <cn_api_tensor_random_randint_like>` ", "返回一个和 x 具有相同形状的服从均匀分布的、范围在[low, high)的随机Tensor，数据类型为 dtype 或者和 x 相同。"
    " :ref:`paddle.randn <cn_api_tensor_random_randn>` ", "返回符合标准正态分布（均值为0，标准差为1的正态随机分布）的随机Tensor"
    " :ref:`paddle.randperm <cn_api_tensor_random_randperm>` ", "返回一个数值在0到n-1、随机排列的1-D Tensor"
    " :ref:`paddle.seed <cn_api_paddle_framework_seed>` ", "设置全局默认generator的随机种子"
    " :ref:`paddle.uniform <cn_api_tensor_uniform>` ", "返回数值服从范围[min, max)内均匀分布的随机Tensor"
    " :ref:`paddle.standard_normal <cn_api_tensor_random_standard_normal>` ", "返回符合标准正态分布（均值为0，标准差为1的正态随机分布）的随机Tensor，形状为 shape，数据类型为 dtype"

.. _tensor_linalg:

tensor线性代数相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.bincount <cn_api_tensor_bincount>` ", "统计输入张量中元素的出现次数"
    " :ref:`paddle.bmm <cn_api_paddle_tensor_bmm>` ", "对输入x及输入y进行矩阵相乘"
    " :ref:`paddle.cross <cn_api_tensor_linalg_cross>` ", "计算张量 x 和 y 在 axis 维度上的向量积（叉积）"
    " :ref:`paddle.dist <cn_api_tensor_linalg_dist>` ", "计算 (x-y) 的 p 范数（p-norm）"
    " :ref:`paddle.dot <cn_api_paddle_tensor_linalg_dot>` ", "计算向量的内积"
    " :ref:`paddle.histogram <cn_api_tensor_histogram>` ", "计算输入张量的直方图"
    " :ref:`paddle.matmul <cn_api_tensor_matmul>` ", "计算两个Tensor的乘积，遵循完整的广播规则"
    " :ref:`paddle.mv <cn_api_tensor_mv>` ", "计算矩阵 x 和向量 vec 的乘积"
    " :ref:`paddle.rank <cn_api_fluid_layers_rank>` ", "计算输入Tensor的维度（秩）"
    " :ref:`paddle.t <cn_api_paddle_tensor_t>` ", "对小于等于2维的Tensor进行数据转置"
    " :ref:`paddle.tril <cn_api_tensor_tril>` ", "返回输入矩阵 input 的下三角部分，其余部分被设为0"
    " :ref:`paddle.triu <cn_api_tensor_triu>` ", "返回输入矩阵 input 的上三角部分，其余部分被设为0"

.. _tensor_manipulation:

tensor元素操作相关（如：转置，reshape等）
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.broadcast_to <cn_api_tensor_broadcast_to>` ", "根据 shape 指定的形状广播 x ，广播后， x 的形状和 shape 指定的形状一致"
    " :ref:`paddle.broadcast_tensors <cn_api_paddle_broadcast_tensors>` ", "对一组输入Tensor进行广播操作, 输入应符合广播规范"
    " :ref:`paddle.cast <cn_api_fluid_layers_cast>` ", "将输入的x的数据类型转换为 dtype 并输出"
    " :ref:`paddle.chunk <cn_api_tensor_cn_chunk>` ", "将输入Tensor分割成多个子Tensor"
    " :ref:`paddle.concat <cn_api_tensor_concat>` ", "对输入沿 axis 轴进行联结，返回一个新的Tensor"
    " :ref:`paddle.crop <cn_api_paddle_crop>` ", "根据偏移量（offsets）和形状（shape），裁剪输入（x）Tensor"
    " :ref:`paddle.expand <cn_api_tensor_expand>` ", "根据 shape 指定的形状扩展 x ，扩展后， x 的形状和 shape 指定的形状一致"
    " :ref:`paddle.expand_as <cn_api_tensor_expand_as>` ", "根据 y 的形状扩展 x ，扩展后， x 的形状和 y 的形状相同"
    " :ref:`paddle.flatten <cn_api_paddle_flatten>` ", "根据给定的start_axis 和 stop_axis 将连续的维度展平"
    " :ref:`paddle.flip <cn_api_tensor_flip>` ", "沿指定轴反转n维tensor"
    " :ref:`paddle.rot90 <cn_api_tensor_rot90>` ", "沿axes指定的平面将n维tensor旋转90度k次"
    " :ref:`paddle.gather <cn_api_paddle_tensor_gather>` ", "根据索引 index 获取输入 x 的指定 aixs 维度的条目，并将它们拼接在一起"
    " :ref:`paddle.gather_nd <cn_api_tensor_cn_gather_nd>` ", "paddle.gather的高维推广"
    " :ref:`paddle.reshape <cn_api_fluid_layers_reshape>` ", "在保持输入 x 数据不变的情况下，改变 x 的形状"
    " :ref:`paddle.reshape_ <cn_api_paddle_tensor_reshape_>` ", "Inplace 版本的 reshape API，对输入 x 采用 Inplace 策略"
    " :ref:`paddle.roll <cn_api_tensor_manipulation_roll>` ", "沿着指定维度 axis 对输入 x 进行循环滚动，当元素移动到最后位置时，会从第一个位置重新插入"
    " :ref:`paddle.scatter <cn_api_distributed_scatter>` ", "通过基于 updates 来更新选定索引 index 上的输入来获得输出"
    " :ref:`paddle.scatter_ <cn_api_paddle_cn_scatter_>` ", "Inplace 版本的 scatter API，对输入 x 采用 Inplace 策略 "
    " :ref:`paddle.scatter_nd <cn_api_fluid_layers_scatter_nd>` ", "根据 index ，将 updates 添加到一个新的张量中，从而得到输出的Tensor"
    " :ref:`paddle.scatter_nd_add <cn_api_fluid_layers_scatter_nd_add>` ", "通过对Tensor中的单个值或切片应用稀疏加法，从而得到输出的Tensor"
    " :ref:`paddle.shard_index <cn_api_fluid_layers_shard_index>` ", "根据分片（shard）的偏移量重新计算分片的索引"
    " :ref:`paddle.slice <cn_api_paddle_slice>` ", "沿多个轴生成 input 的切片"
    " :ref:`paddle.split <cn_api_distributed_split>` ", "将输入Tensor分割成多个子Tensor"
    " :ref:`paddle.squeeze <cn_api_paddle_tensor_squeeze>` ", "删除输入Tensor的Shape中尺寸为1的维度"
    " :ref:`paddle.squeeze_ <cn_api_paddle_tensor_squeeze_>` ", "Inplace 版本的 squeeze API，对输入 x 采用 Inplace 策略"
    " :ref:`paddle.stack <cn_api_paddle_tensor_stack>` ", "沿 axis 轴对输入 x 进行堆叠操作"
    " :ref:`paddle.strided_slice <cn_api_strided_slice>` ", "沿多个轴生成 x 的切片"
    " :ref:`paddle.tile <cn_api_tensor_tile>` ", "根据参数 repeat_times 对输入 x 的各维度进行复制"
    " :ref:`paddle.transpose <cn_api_fluid_layers_transpose>` ", "根据perm对输入的多维Tensor进行数据重排"
    " :ref:`paddle.tensordot <cn_api_paddle_tensordot>`  ", "沿多个轴对输入的x和y进行张量缩并操作"
    " :ref:`paddle.unbind <cn_api_paddle_tensor_unbind>` ", "将输入Tensor按照指定的维度分割成多个子Tensor"
    " :ref:`paddle.unique <cn_api_tensor_cn_unique>` ", "返回Tensor按升序排序后的独有元素"
    " :ref:`paddle.unique_consecutive <cn_api_tensor_cn_unique_consecutive>` ", "返回无连续重复元素的Tensor"
    " :ref:`paddle.unsqueeze <cn_api_paddle_tensor_unsqueeze>` ", "该OP向输入Tensor的Shape中一个或多个位置（axis）插入尺寸为1的维度"
    " :ref:`paddle.unsqueeze_ <cn_api_paddle_tensor_unsqueeze_>` ", "Inplace 版本的 unsqueeze API，对输入 x 采用 Inplace 策略"
    " :ref:`paddle.unstack <cn_api_fluid_layers_unstack>` ", "该OP将单个dim为 D 的Tensor沿 axis 轴unpack为 num 个dim为 (D-1) 的Tensor"

.. einsum:

爱因斯坦求和
::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.einsum <cn_api_tensor_einsum>` ", "根据爱因斯坦标记对多个张量进行爱因斯坦求和"

.. _about_framework:

framework相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.CPUPlace <cn_api_fluid_CPUPlace>` ", "一个设备描述符，指定CPUPlace则Tensor将被自动分配在该设备上，并且模型将会运行在该设备上"
    " :ref:`paddle.CUDAPinnedPlace <cn_api_fluid_CUDAPinnedPlace>` ", "一个设备描述符，它所指代的页锁定内存由 CUDA 函数 cudaHostAlloc() 在主机内存上分配，主机的操作系统将不会对这块内存进行分页和交换操作，可以通过直接内存访问技术访问，加速主机和 GPU 之间的数据拷贝"
    " :ref:`paddle.CUDAPlace <cn_api_fluid_CUDAPlace>` ", "一个设备描述符，表示一个分配或将要分配 Tensor 或 LoDTensor 的 GPU 设备"
    " :ref:`paddle.DataParallel <cn_api_fluid_dygraph_DataParallel>` ", "通过数据并行模式执行动态图模型"
    " :ref:`paddle.NPUPlace <cn_api_fluid_NPUPlace>` ", "一个设备描述符，指NCPUPlace则Tensor将被自动分配在该设备上，并且模型将会运行在该设备上"
    " :ref:`paddle.disable_signal_handler <cn_api_fluid_disable_signal_handler>` ", "关闭Paddle系统信号处理方法"
    " :ref:`paddle.disable_static <cn_api_paddle_disable_static>` ", "关闭静态图模式"
    " :ref:`paddle.enable_static <cn_api_paddle_enable_static>` ", "开启静态图模式"
    " :ref:`paddle.get_default_dtype <cn_api_paddle_framework_get_default_dtype>` ", "得到当前全局的dtype"
    " :ref:`paddle.grad <cn_api_paddle_grad>` ", "对于每个 inputs ，计算所有 outputs 相对于其的梯度和"
    " :ref:`paddle.in_dynamic_mode <cn_api_paddle_in_dynamic_mode>` ", "查看paddle当前是否在动态图模式中运行"
    " :ref:`paddle.load <cn_api_paddle_framework_io_load>` ", "从指定路径载入可以在paddle中使用的对象实例"
    " :ref:`paddle.no_grad <cn_api_fluid_dygraph_no_grad>` ", "创建一个上下文来禁用动态图梯度计算"
    " :ref:`paddle.ParamAttr <cn_api_fluid_ParamAttr>` ", "创建一个参数属性对象"
    " :ref:`paddle.save <cn_api_paddle_framework_io_save>` ", "将对象实例obj保存到指定的路径中"
    " :ref:`paddle.set_default_dtype <cn_api_paddle_framework_set_default_dtype>` ", "设置默认的全局dtype。"
    " :ref:`paddle.set_grad_enabled <cn_api_paddle_framework_set_grad_enabled>` ", "创建启用或禁用动态图梯度计算的上下文"
    " :ref:`paddle.set_printoptions <cn_api_tensor_set_printoptions>` ", "设置 paddle 中 Tensor 的打印配置选项"

.. _about_device:
device相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.get_cuda_rng_state <cn_api_paddle_cn_get_cuda_rng_state>` ", "获取cuda随机数生成器的状态信息"
    " :ref:`paddle.set_cuda_rng_state <cn_api_paddle_cn_set_cuda_rng_stat>` ", "设置cuda随机数生成器的状态信息"

.. _about_hapi:

高层API相关
::::::::::::::::::::

.. csv-table::
    :header: "API名称", "API功能"
    :widths: 10, 30

    " :ref:`paddle.Model <cn_api_paddle_Model>` ", "一个具备训练、测试、推理的神经网络"
    " :ref:`paddle.summary <cn_api_paddle_summary>` ", "打印网络的基础结构和参数信息"
    " :ref:`paddle.flops <cn_api_paddle_flops>` ", "打印网络的基础结构和参数信息"
