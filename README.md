# qwen3_vl_rknn_rk3576
#
#这是对qwen3_vl的rknn平台测试demo的改进，使用的是rk3576平台
#改进点在于可以在终端的对话中，使用：load_image 路径     来更换图片。
#解决原demo的更换图片进行对话需要重新加载llm模型，较为耗时
#对比：
qwen3-vl-2B模型：
LLM 模型加载	5051.29 ms	≈5.1 秒
ImgEnc 模型加载	1522.56 ms	≈1.5 秒	
ImgEnc 推理	1858.58 ms	≈1.9 秒

qwen3-vl-4B模型：
RKLLM 模型加载	14492.72 ms≈14.5 秒
ImgEnc 模型加载	4830.93 ms	≈4.8 秒
ImgEnc 推理	1902.91 ms	≈1.9 秒
#
#
#改进后每次更换图片在终端对话中进行，仅需要ImgEnc 推理	1902.91 ms	≈1.9 秒时间。
