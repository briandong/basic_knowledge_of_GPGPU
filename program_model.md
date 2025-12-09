# GPGPU编程模型

## 步骤

在CUDA的编程模型中，会将运行在CPU和GPGPU上的代码分别称为host代码和device代码，并用关键字标记。

Host代码通常分为三个步骤：
1. 数据复制
2. 启动GPGPU
3. 数据写回

## 线程结构

CUDA的线程结构分为三级，由上到下分别是：grid, block, thread。

其中grid的数量由三维数组（x-行，y-列，z-深度）gridDim指定；block的数量由三维数组blockDim指定。

CUDA使用blockIdx和threadIdx来索引grid中每个thread的位置。

## 实例

矩阵乘法实例
```c
# 数据复制
float A[M * N], B[N * K], C[M * K];               # host数据声明
float * d_A, * d_B, * d_C;                        # device数据声明
int size=M * N * sizeof(float);
cudaMalloc((void **)&d_A, size);                  # device空间分配
cudaMemcpy(d_A, A, size, cudaMemcpyHostToDevice); # 数据复制
size=N * K * sizeoffloat);
cudaMalloc((void **)&d_B, size);
cudaMemcpy(d_B, B, size, cudaMemcpyHostToDevice)；
size=M * K * sizeof(float);
cudaMalloc((void **)&d_C, size);

# 启动GPGPU
unsigned T_size=16;
dim3 gridDim(M/T_size, K/T_size, 1）;
dim3 blockDim（T_size, T_size, 1);
basic_mul <<<gridDim, blockDim>>> (d_A,d_B,d_C); # 启动device代码
cudaDeviceSynchronize();                         # 同步host与device

# 数据写回
size=M * K * sizeof(float);
cudaMemcpy(C,d_C, size, cudaMemcpyDeviceToHost); # device数据写回host
cudaFree(d_A); cudaFree(d_B); cudaFree(d_C);     # device空间释放
return 0；

# kernel函数，关键字__global__，在GPGPU上执行
__global__ void basic_mul(float * d_A, float * d_B, float * d_C)
{
    int row=threadldx.x + blockIdx.x * blockDim.x;
    int col=threadIdx.y + blockIdx.y * blockDim.y;
    for（int i=0; i<N; i++)
    {
        d_C[row * K + col] += d_A[row * N + i] * d_B[col + i * K];
    }
}
```
