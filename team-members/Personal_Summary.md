# CRAFT Project – Personal Summary

## Dylan
### My contributions

My work focused on understanding the CRAFT architecture, preparing the ACCESS-SY data workflow, and developing a small notebook to test the model pipeline. I contributed to reviewing CRAFT and NVIDIA ATLAS and documenting the hourly U/V wind data, preprocessing decisions and tensor interfaces. I also prepared a technical documentation draft covering reproducibility requirements and outstanding work.

The local synthetic-data smoke test successfully checked data loading, encoding, latent evolution and decoding over six hourly forecast steps. This confirmed that the basic data flow and forward/backward pass worked at small scale.

### What I learned

I gained experience with NetCDF, xarray and PyTorch, particularly in preparing wind data and managing spatiotemporal tensor shapes. I learned why chronological validation and training-only normalization are necessary to avoid data leakage. The project also helped me understand the difference between getting a model pipeline running and demonstrating useful forecasting performance.

### Remaining work

The prototype uses a simplified ConvGRU-style temporal component. Further work includes implementing the planned Transformer, validating on genuine ACCESS-SY data, correcting the split and normalization procedure, and comparing forecasts against a persistence baseline. The final environment, configurations and results also need to be recorded for reproducibility.
