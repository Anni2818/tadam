## tadam
instructions to run the project:

# add .env file first


# mcp gateway -
cd /workspaces/tadam/telehealth/genaicapstone
source .venv/bin/activate
python -m app.mcp_server.gateway

after starting the gateway go into the forwarded ports and make visibility of 8001 public.
if the port is not already present then add it manually.

# backend - 
cd /workspaces/tadam/telehealth/genaicapstone
source .venv/bin/activate
python -m uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload

# frontend - 
cd /workspaces/tadam/telehealth/genaicapstone
source .venv/bin/activate
python -m streamlit run streamlit_app.py \
  --server.address 0.0.0.0 \
  --server.port 8501
 
